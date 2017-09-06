<template>
  <div>
    <h1>상세 내용</h1>
    {{ movie }}
  </div>
</template>

<script>
export default {
  data () {
    return {
      movie: {}
    }
  },
  created () {
    var id = this.$route.params.id
    this.$http.get('/api/movies/' + id)
    .then((response) => {
      this.movie = response.data
    })
  }
}
</script>

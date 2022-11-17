<template>
  <div class="secret"
    :style="{
      'backgroundImage' : 'url(' + require('@/assets/img/index/bg3.png') + ')'
    }"
  >
    <iframe src="https://docs.google.com/forms/d/e/1FAIpQLSfd6NNOtLe5hhKNlVD7gt6QxASHqKbKOyBsVdnpargTeTuk9A/viewform?embedded=true" width="640" height="937" frameborder="0" marginheight="0" marginwidth="0">載入中…</iframe>
  </div>
</template>

<script>


export default {
  layout: 'default',
  components: {

  },
  props: {

  },
  data () {
    return {
      
    }
  },
  async mounted () {

  },
  destroyed () {
    
  },
  computed: {
    
  },
  methods: {
    
    
  },
  watch: {
    
  }
}
</script>

<style lang="scss" scoped>

.secret {
  display: flex;
  justify-content: center;
  padding: 100px 0px 40px;
  background-repeat: no-repeat;
  background-size: cover;
  background-position-x: center;
  background-position-y: center;
}

</style>

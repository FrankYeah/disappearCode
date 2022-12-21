<template>
  <div class="secret"
    :style="{
      'backgroundImage' : 'url(' + require('@/assets/img/index/bg3.png') + ')'
    }"
  >
    <iframe width="100%" height="600px" src="https://www.surveycake.com/s/Y6347"
    style="border:#ddd 1px solid;" allowTransparency="true" frameborder="0"></iframe>
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

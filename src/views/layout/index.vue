<template>
  <div class="layout">
      <div>
          <Header :info='info'></Header>
      </div>
      <div>
          <router-view @show="show" :info='info'/>
      </div>
      <right-nav class="rightnav"></right-nav>
      <div>
          <Footer :info='info'></Footer>
      </div>
  </div>
</template>

<script>
import Header from './components/header'
import Footer from './components/footer'
import rightNav from '../../components/rightNav'
export default {
    components: { Header, Footer, rightNav },
    data () {
        return {

        }
    },
    created () {
    },
    methods: {

    }
}
</script>

<style lang='scss' scoped>
.layout{
    width: 100%;
    height: 100%;
    position: relative;
}
.rightnav{
        position: fixed;
        top: 244px;
        right: 2%;
        margin-left: 620px;
        z-index: 999;
    }
</style>

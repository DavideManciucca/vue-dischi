<template>
  <div >
    <div class="container-fluid">
    <HeaderComp />
    <MainComp />
    </div>
  </div>
</template>

<script>
import HeaderComp from '@/components/HeaderComp';
import MainComp from '@/components/MainComp';


export default {
  name: 'App',
  components: {
   HeaderComp,
   MainComp
  }
}
</script>
<style lang="scss">
@import './assets/style/vars';
@import './assets/style/general'
</style>

<template>
  <div class="header">
    <div><img src="" alt="">logo</div>
    <div> <input placeholder="Cerca qui il tuo brano!!" type="text"> </div>
  </div>
</template>

<script>
export default {
  name:'HeaderComp'
}
</script>

<style lang="scss" scoped> 
  .header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 50px;
    background-color: #2e3a46;
  }
</style>
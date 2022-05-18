<template>
  <div class="header">
    <div><img src="" alt="">logo</div>
    <div> 
      <form>
      <select v-model="selected" name="" id="">
        <option value="All">All</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
      </select>
      </form>
    </div>
  </div>
</template>

<script>

export default {
  name:'HeaderComp',
  data(){
      
  }
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
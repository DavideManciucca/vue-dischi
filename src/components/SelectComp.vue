<template>
  <div class="dm-cont-top">
    <div>LOGO</div>
    <div><form>
      <select v-model="genere" @change="$emit('changedGenre', genere)" name="" id="">
        <option value="All">All</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
      </select>
      </form></div>
  </div>
</template>

<script>
export default {
    name:'SelectComp',
    data(){
      return{
        genere: 'All'
      }
    },
    methods : {
      valoreCambiato : function() {

        console.log(this.genere);
      }
    }
}
</script>

<style langh="scss" scoped>
.dm-cont-top{
  display: flex;
  justify-content: space-between;
  background-color: #2e3a46;
}

</style>
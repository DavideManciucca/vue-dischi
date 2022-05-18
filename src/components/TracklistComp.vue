<template>
  
   
     <div class="dm-track">
       <div class="poster">
      <img :src="trackValue.poster" alt="trackValue.title">
       </div>
      <h4>{{trackValue.title}}</h4>
      <p class="author">{{trackValue.author}}</p>
      <p class="year">{{trackValue.year}}</p>
    </div>
   
  
</template>

<script>
export default {
  name:'TracklistComp',
  props:{
    trackValue: Object
  }
}
</script>

<style lang="scss" scoped>
.poster img{
  height: 150px;
  width: 150px;
  margin-bottom:8px ;
}
.dm-track{
  // width: 150px;
  // height: 200px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: center;
  flex-basis: 15%;
  background-color: #2e3a46;
  // padding: 8px;
  margin: 1rem;
}.dm-track h4{
  font-size: 12px;
  
  color: white;

}.author{
  font-size: 12px;
  color: grey;
  font-weight: bold;
}.year{
  font-size: 10px;
  color: grey;
  font-weight: bold;


}

</style>
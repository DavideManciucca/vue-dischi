<template>
<div>
  <SelectComp 
  @changedGenre="searchGeneri"
  />
  <div class="dm-wrapper">
  <div class="dm-container">
    <TracklistComp 
    v-for="(track, index) in generiFiltrati" :key="index"
    :trackValue="track"
    />
  </div>
  </div>

  </div>
</template>

<!--

1. il tag selectcomp deve ascoltare l'evento scatenato da lui internmente
2. memorizzo il genere filtrato in un data qui
3. fare una computed properties per filtrare gli album che hanno quell'evento
4. usare quella invece di coverTrackList su v-for

-->

<script>
  import axios from 'axios';
  import TracklistComp from './TracklistComp';
  import SelectComp from './SelectComp'
 

export default {
  name:'MainComp',
  components:{
    TracklistComp,
    SelectComp
    
  },
  data(){
    return{
      myApiUrl:'https://flynn.boolean.careers/exercises/api/array/music',
      coverTrackList:[],
      trackFiltered:'',
    }
  },
  mounted(){
    this.getAPI();
  },
  methods:{
    getAPI(){
      axios.get(this.myApiUrl)
      .then(r=>{
        console.log(r.data.response);

        this.coverTrackList = r.data.response;
      })
      .catch(e=>{
        console.log(e);
      })
    },
    searchGeneri(findGeneri){
      this.trackFiltered = findGeneri
      console.log(this.trackFiltered)
    }

  },

  computed:{
      generiFiltrati(){
        let trackGenere = [];
        if(this.trackFiltered === 'All'){
          trackGenere = this.coverTrackList;
        }else{
          trackGenere= this.coverTrackList.filter(trackCard=>{
            return trackCard.genre.includes(this.trackFiltered)
          })
        }
        return trackGenere;
      }

    //  generiFiltrati(){

      //  let arrFiltratoGeneri = [];
      //  if(arrFiltratoGeneri = this.coverTrackList.filter(trackCard=>{
      //    return trackCard.genre.include(this.findGeneri)
      //  }))
      
    //    if(arrFiltratoGeneri = this.coverTrackList.filter(trackCard =>{
    //      return trackCard.genre.include(this.findGeneri)
    //    }) )
        // return arrFiltratoGeneri;
    
    
  }

}
</script>

<style langh="scss" scoped>
.dm-container{
  display: flex;
  flex-wrap: wrap;
 justify-content: center;
 background-color: #1e2d3b;
 min-height: 100%;
}.dm-wrapper{
  min-height: 100vh;
 background-color: #1e2d3b;

}

</style>
<template>
  <div class="dm-container">
    <TracklistComp 
    v-for="(track, index) in coverTrackList" :key="index"
    :trackValue="track"
    />
  </div>
</template>

<script>
  import axios from 'axios';
  import TracklistComp from './TracklistComp';

export default {
  name:'MainComp',
  components:{
    TracklistComp
  },
  data(){
    return{
      myApiUrl:'https://flynn.boolean.careers/exercises/api/array/music',
      coverTrackList:[],
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
    }
  }
}
</script>

<style langh="scss" scoped>
.dm-container{
  display: flex;
  flex-wrap: wrap;
 justify-content: center;
 background-color: #1e2d3b;
 height: 100vh;
}

</style>
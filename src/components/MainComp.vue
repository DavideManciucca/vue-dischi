<template>
  <div>
    <TracklistComp />
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
        console.log(r.data);
      })
      .catch(e=>{
        console.log(e);
      })
    }
  }
}
</script>

<style langh="scss" scoped>

</style>
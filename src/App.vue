<template>
  <div id="app">
   <autorize @event='autorizeEvent' v-if='autorizeVisible'/>
   <appheader @event='appheaderEvent' v-if="isVisible"/>
   <taskblock v-if="isVisible"/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import autorize from './components/autorization.vue';
import taskblock from './components/taskblock.vue';
import appheader from './components/appheader.vue'

export default {
  components: {
    autorize,
    taskblock,
    appheader
  },
  data(){
    return{
      isVisible: false,
      autorizeVisible: true,
    }
  },
  methods:{
    autorizeEvent(){
      this.isVisible =!this.isVisible;
      this.autorizeVisible = false;
    },
    appheaderEvent(){
      this.isVisible =!this.isVisible;
      this.autorizeVisible = true;
    }
  }
}
</script>

<style>
ul{
  display: block;
  margin-block-start: 0em;
  margin-block-end: 0em;
  margin-inline-start: 0px;
  margin-inline-end: 0px;
  padding-inline-start: 0px;
}
li{
  list-style: none;
}
h3{
    display: block;
    font-size: 1.17em;
    margin-block-start: 0em;
    margin-block-end: 0em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    font-weight: bold;
}
</style>

<template>
  <div class="m-hcity">
    <dl>
      <dt>热门城市：</dt>
      <dd
        v-for="item in list"
        :key="item.id">
        {{ item.name==='市辖区'?item.province:item.name }}
      </dd>
    </dl>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    data(){
      return {
        list:[]
      }
    },
    async mounted(){
      let self = this
      let {status, data: {hots}} = await self.$axios.get('/geo/hotCity')
      if(status === 200){
        self.list = hots
      }
    }
  }
</script>

<style lang='scss'>
  @import "@/assets/css/changeCity/hot.scss";
</style>

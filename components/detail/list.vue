<template>
  <div class="m-detail-list">
    <ul>
      <li>{{ list.filter(item=>item.photos.length).length }}款套餐</li>
      <item
        v-for="(item,idx) in list"
        :key="idx"
        :meta="item" />
    </ul>
  </div>
</template>

<script type="text/ecmascript-6">
  import Item from './item.vue'
  export default {
    components: {
      Item
    },
    props: {
      list: {
        type:Array,
        default:()=>{
          return []
        }
      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus"></style>

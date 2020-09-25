<template>
  <div>
    <Navbar></Navbar>
    <div class="container">
      <div class="col-12 mt-5">
        <Rank
          v-for="(rank, i) in ranks"
          :key="i" class="my-2"
          :title="rank.title"
          :draggableGroupName="draggableGroupName"
          :bgColor="rank.bgColor"
          :index="i" />
      </div>
      <div class="col-12">
        <ItemsStock :draggableGroupName="draggableGroupName" />
      </div>
    </div>
  </div>
</template>

<script>
  import Navbar from '~/components/Navbar.vue'
  import Rank from '~/components/Rank.vue'
  import ItemsStock from '~/components/ItemsStock.vue'

export default {
  components: {
    Navbar,
    Rank,
    ItemsStock
  },
  data() {
    return {
      draggableGroupName: 'draggable-item',
      ranks: [
        {title: 'Rank S', bgColor: '#3AB795'},
        {title: 'Rank A', bgColor: '#82D173'},
        {title: 'Rank B', bgColor: '#FFB140'},
        {title: 'Rank C', bgColor: '#DB504A'}
      ]
    }
  }
}
</script>

<style>
  body {
    font-family: 'Raleway', sans-serif;
  }
</style>

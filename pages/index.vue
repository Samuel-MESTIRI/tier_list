<template>
  <div>
    <Navbar></Navbar>
    <div class="container">
      <div class="col-12 mt-5">
        <Rank v-for="(rank, i) in ranks" :key="i" class="m-2" :title="rank.title" />
      </div>
      <div class="col-12">
        <ItemsStock />
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
      ranks: [
        {title: 'rank S'},
        {title: 'rank A'},
        {title: 'rank B'},
        {title: 'rank C'},
        {title: 'rank D'},
      ]
    }
  }
}
</script>


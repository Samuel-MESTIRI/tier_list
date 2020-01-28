<template>
  <div>
    <Navbar></Navbar>
    <div class="container">
      <div class="col-12 mt-5">
        <Rank></Rank>
      </div>
    </div>
  </div>
</template>

<script>
  import Navbar from '~/components/Navbar.vue'
  import Rank from '~/components/Rank.vue'

export default {
  components: {
    Navbar,
    Rank
  }
}
</script>


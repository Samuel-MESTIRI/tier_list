<template>
  <div class="rank border d-flex">
    <div class="rank-title border border-info d-flex align-items-center bg-info text-white h-100">
      <textarea
        type="text"
        class="text-center w-100 text-white"
        maxlength="55"
        v-model="title"
      ></textarea>
    </div>
    <div class="item border m-2">
      <img src="~/static/img-test.jpg">
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      title: {
        type: String,
        required: true
      }
    },
    data() {
      return {
        rankTitle: 'Le super titre'
      }
    }
  }
</script>

<style>
  .rank {
    height: 100px;
    box-sizing: border-box;
    box-shadow: 0 0 10px rgba(0,0,0,0.25);
  }
  .rank-title {
    width: 20%;
    resize: none;
  }
  .rank-title textarea {
    resize: none;
    border: none;
    background-color: transparent;
  }
  .rank-title textarea:focus {
    outline-color: transparent;
  }
  .item img {
    width: 80px;
    height: 80px;
  }
</style>



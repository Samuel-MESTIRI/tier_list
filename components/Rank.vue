<template>
  <div class="rank border">
    <div class="rank-title border border-info d-flex align-items-center bg-info text-white h-100">
      <textarea
        type="text"
        class="text-center w-100"
        maxlength="55"
        v-model="rankTitle"
      ></textarea>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        rankTitle: 'Le super titre'
      }
    }
  }
</script>

<style>
  .rank {
    height: 152px;
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
</style>



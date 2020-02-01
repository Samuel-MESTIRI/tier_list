<template>
  <div class="rank border d-flex">
    <div
      class="rank-title text-white d-flex align-items-center"
      :style="'background-color:' + bgColor"
    >
      <div class="text-center w-100 text-white" contenteditable="true">
        {{ title }}
      </div>
    </div>
    <draggable :list="itemList" :group="draggableGroupName" class="w-100">
      <img
        v-for="item in itemList"
        :key="item.id"
        :src="item.name"
        class="item border m-2 cursor"
      >
    </draggable>
  </div>
</template>

<script>
  import draggable from 'vuedraggable'
  export default {
    props: {
      title: {
        type: String,
        required: true
      },
      draggableGroupName: {
        type: String,
        required: true
      },
      bgColor: {
        type: String,
        required: true
      },
      index: {
        type: Number,
        required: true
      }
    },
    components: {
      draggable
    },
    data() {
      return {
        itemList: []
      }
    }
  }
</script>

<style>
  .rank {
    min-height: 100px;
    height: inherit !important;
    box-sizing: border-box;
    box-shadow: 0 0 10px rgba(0,0,0,0.25);
  }
  .rank-title {
    max-width: 180px;
    width: 180px;
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
  .item {
    width: 80px;
    height: 80px;
    cursor: pointer;
  }
</style>



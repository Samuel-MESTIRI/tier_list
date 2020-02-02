<template>
  <div id="item-stock" class="my-5 pl-4 p-2">
    <h2 class="mb-3 mt-2">Classe tes cartes du meilleur au moins bon !</h2>
    <draggable :list="itemList" :group="draggableGroupName" class="w-100">
      <img
        v-for="item in itemList"
        :key="item.id"
        :src="item.name"
        class="item border m-2"
      >
    </draggable>
    <button
      class="btn add-theme-btn position-absolute text-white"
      v-b-modal.theme-choice-modal>
            +
    </button>
    <b-modal id="theme-choice-modal" size="xl" title="Choix des thèmes">
      <ThemeChoiceModal></ThemeChoiceModal>
    </b-modal>
  </div>
</template>

<script>

  import draggable from 'vuedraggable'
  import ThemeChoiceModal from '~/components/ThemeChoiceModal.vue'
  export default {
    props: {
      draggableGroupName: {
        type: String,
        required: true
      }
    },
    components: {
      draggable,
      ThemeChoiceModal
    },
    data() {
      return {
        itemList: [
          {name: require('~/static/img1.jpg'), id: 1},
          {name: require('~/static/img2.jpg'), id: 2},
          {name: require('~/static/img3.jpg'), id: 3},
          {name: require('~/static/img4.jpg'), id: 4},
          {name: require('~/static/img4.jpg'), id: 5},
          {name: require('~/static/img4.jpg'), id: 6},
          {name: require('~/static/img4.jpg'), id: 7},
          {name: require('~/static/img4.jpg'), id: 8},
          {name: require('~/static/img4.jpg'), id: 9},
          {name: require('~/static/img4.jpg'), id: 10},
          {name: require('~/static/img4.jpg'), id: 11},
          {name: require('~/static/img4.jpg'), id: 12},
          {name: require('~/static/img4.jpg'), id: 13},
          {name: require('~/static/img4.jpg'), id: 14},
          {name: require('~/static/img4.jpg'), id: 15},
          {name: require('~/static/img4.jpg'), id: 16},
          {name: require('~/static/img4.jpg'), id: 17},
          {name: require('~/static/img4.jpg'), id: 18}
        ]
      }
    }
  }
</script>

<style>
#item-stock {
  border-left: 30px #82D173 solid !important;
  min-height: 98px;
  box-shadow: 0 0 10px rgba(0,0,0,0.25);
}
.add-theme-btn {
  background-color: #82D173;
  font-size: 6rem;
  border-radius: 50%;
  height: 80px;
  width: 80px;
  line-height: 0;
  top: 50%;
  right: -20px;
  transform: translate(0,-50%);
}
</style>




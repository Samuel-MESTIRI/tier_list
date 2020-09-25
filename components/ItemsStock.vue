<template>
  <div id="item-stock" class="my-5 pl-4 p-2">
    <div v-if="themeChoosen">
      <h2 class="mb-3 mt-2">Classe tes cartes du meilleur au moins bon !</h2>
      <draggable :list="themeChoosen.images" :group="draggableGroupName" class="w-100">
        <img
          v-for="item in themeChoosen.images"
          :key="item.id"
          :src="item.name"
          class="item border m-2"
        >
      </draggable>
      <button
        class="btn add-theme-btn position-absolute text-white p-0"
        v-b-modal.theme-choice-modal>
        <i class="material-icons">cached</i>
      </button>
    </div>
    <div v-else class="d-flex justify-content-center align-items-center" style="height: 90px">
      <button class="btn text-white p-3 font-weight-bold" v-b-modal.theme-choice-modal>Choisir un theme</button>
    </div>
    <ThemeChoiceModal @setNewTheme="setNewTheme"></ThemeChoiceModal>
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
        themeChoosen: null
      }
    },
    methods: {
      setNewTheme(value) {
        console.log(value)
        this.themeChoosen = value
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
.add-theme-btn i {
  font-size: 36px;
}
.btn {
  background-color: #82D173;
}
</style>




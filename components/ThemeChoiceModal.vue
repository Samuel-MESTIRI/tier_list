<template>
  <div>
    <b-modal id="theme-choice-modal" size="xl" title="Choix des thèmes">
      <div class="d-flex flex-row">
        <div
          v-for="(theme, i) in themes"
          :key="i"
          class="theme-choice-item d-flex flex-column text-center m-2 font-weight-bold"
          :class="theme.id === selectedTheme ? 'theme-selected' : ''"
          @click="setTheme(theme.id)"
        >
          {{ theme.name }}
          <img :src="theme.themeImg" :alt="'img de ' + theme.name">
        </div>
      </div>
      <template v-slot:modal-footer>
        <div class="w-100 d-flex justify-content-end">
          <button class="btn text-white" @click="chooseTheme">Ajouter</button>
        </div>
      </template>
    </b-modal>
  </div>
</template>

<script>

  export default {
    data() {
      return {
        selectedTheme: null,
        themes: [
          {
            name: 'soda',
            id: 1,
            themeImg: require('~/static/soda/theme.jpg'),
            images: [
              {name: require('~/static/soda/img1.jpg'), id: 1},
              {name: require('~/static/soda/img2.jpg'), id: 2},
              {name: require('~/static/soda/img3.png'), id: 3},
              {name: require('~/static/soda/img4.jpg'), id: 4},
              {name: require('~/static/soda/img5.png'), id: 5},
              {name: require('~/static/soda/img6.jpg'), id: 6},
              {name: require('~/static/soda/img7.jpg'), id: 7},
              {name: require('~/static/soda/img8.jpg'), id: 8},
              {name: require('~/static/soda/img9.jpg'), id: 9},
              {name: require('~/static/soda/img10.jpg'), id: 10},
              {name: require('~/static/soda/img11.jpg'), id: 11},
              {name: require('~/static/soda/img12.jpg'), id: 12},
              {name: require('~/static/soda/img13.jpg'), id: 13},
            ]
          },
          {
            name: 'Fast food',
            id: 2,
            themeImg: require('~/static/fastfood/theme.png'),
            images: [
              {name: require('~/static/fastfood/img1.jpg'), id: 1},
              {name: require('~/static/fastfood/img2.jpg'), id: 2},
              {name: require('~/static/fastfood/img3.jpg'), id: 3},
              {name: require('~/static/fastfood/img4.png'), id: 4},
              {name: require('~/static/fastfood/img5.png'), id: 5},
              {name: require('~/static/fastfood/img6.jpg'), id: 6},
              {name: require('~/static/fastfood/img7.png'), id: 7},
              {name: require('~/static/fastfood/img8.png'), id: 8},
              {name: require('~/static/fastfood/img9.jpg'), id: 9},
              {name: require('~/static/fastfood/img10.jpg'), id: 10},
            ]
          }
        ]
      }
    },
    methods: {
      setTheme(themeId) {
        this.selectedTheme = themeId
      },
      chooseTheme() {
        const theme = this.themes.find(el => el.id === this.selectedTheme)
        this.$emit('setNewTheme', theme)
        this.$bvModal.hide('theme-choice-modal')
      }
    }
  }
</script>

<style>
  #theme-choice-modal .modal-dialog {
    margin-top: 100px;
    height: 80%;
  }
  #theme-choice-modal .modal-content {
    height: 100%;
    border: none;
    border-radius: 0;
  }
  .theme-choice-item {
    font-weight: 500;
    width: 116px;
    box-sizing: border-box;
    padding: 8px;
    box-shadow: 0 0 10px rgba(0,0,0,0.25);
  }
  .theme-choice-item:hover {
    box-shadow: 0 0 30px rgba(0,0,0,0.25);
    cursor: pointer;
  }

  .theme-choice-item img {
    width: 100px;
    height: 100px;
  }
  .theme-selected {
    background-color: #82D173;
    color: white;
  }
</style>





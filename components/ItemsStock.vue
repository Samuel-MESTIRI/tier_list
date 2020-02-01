<template>
  <div class="col-12 p-5">
    <draggable v-model="myArray" draggable=".item" group="people">
      <div v-for="element in myArray" :key="element.id" class="item border border-dark">
        {{element.name}}
      </div>
    </draggable>
    <div class="m-5">separator</div>
    <draggable v-model="myArray2" draggable=".item" group="people">
      <div v-for="element in myArray2" :key="element.id" class="item border border-dark">
        {{element.name}}
      </div>
    </draggable>
  </div>
</template>

<script>

  import draggable from 'vuedraggable'
  export default {
    components: {
      draggable,
    },
    data() {
      return {
        hello: 'cc',
        myArray: [
          {name: 'cou1'},
          {name: 'cou2'},
          {name: 'cou3'},
          {name: 'cou4'},
          {name: 'cou5'},
          {name: 'cou6'},
          {name: 'cou7'},
          {name: 'cou8'}
        ],
        myArray2: [
          {name: 'rr1'},
          {name: 'rr2'},
          {name: 'rr3'},
          {name: 'rr4'},
          {name: 'rr5'},
          {name: 'rr6'},
          {name: 'rr7'},
          {name: 'rr8'}
        ]
      }
    }
  }
</script>

<!--<style>
  #items-stock {
    height: 100%;
  }
</style>-->
<style scoped>
  .item {
    width: 40%;
    display: inline-block;
  }
</style>



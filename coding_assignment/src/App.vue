<template>
  <div id="app">
    <div class="row">
        <Sidebar :blocks="blocks" :textFields="textFields"/>
        <div class="col-sm-10" id="top" >
          <div class="row">
            <Block
              v-for="(block, index) in blocks"
              :block="block"
              :index="index"
              :blocks="blocks"
              :textFields="textFields"/>
          </div>
        </div>
        <Summary :textFields="textFields"/>
    </div>
  </div>
</template>

<script>
import Block from './components/Block.vue'
import Sidebar from './components/Sidebar.vue'
import Summary from './components/Summary.vue'

export default {
  name: 'app',
  components: {
    Block,
    Sidebar,
    Summary
  },
  data() {
    return{
      // blocks array will contain the data for the education block and the profession block, including the title and the two labels for each of the blocks.
      blocks: [],
      //textFields array will contain the id of either 1 (for education) or 0 (for profession), as well as the strings that will populate the summary.
      textFields:[],
    }
  },
}
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  padding-top: 30px;
  position: fixed;
}
#top,
#bottom {
    margin-left: 200px;
    position: fixed;
    left: 0;
    right: 0;
    height: 30%;
}

#top {
  position: sticky;
  height: 66vh;
  width: 188vh;
  overflow: auto;
  top: 0;
  right: 0;
}

</style>

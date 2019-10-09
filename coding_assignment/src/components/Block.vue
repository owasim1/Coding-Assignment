<!-- Block is the component that contains the title and the two text-fields
and their labels -->
<template>
  <div class="col-sm-2 fix-constraints">
    <div class="border border-dark rounded" style="width:17rem;"> <!-- Using bootstrap to create a card to give the block borders -->
      <ul class="list-group list-group-flush">
        <li style="background:#424B54" class="list-group-item">
          <h6 class="title">
            {{ block.title }}
            <button type="button" class="close" aria-label="Close" @click="removeElement(index)">
              <span aria-hidden="true">&times;</span>
            </button>
          </h6>
        </li>
        <li class="color list-group-item">
          <label>{{ block.field1 }}</label>
          <input maxlength="40" v-model="topField" @keyup="replaceAtIndexTop" type="text" class="form-control" :placeholder="block.example1">
          <label class="pad">{{block.field2}}</label>
          <input maxlength="15" v-model="bottomField" @keyup="replaceAtIndexBottom" type="text" class="form-control" :placeholder="block.example2">
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import Vue from 'vue'

export default {
  name: 'Block',
  props: ['block', 'index', 'blocks', 'textFields'],
  data() {
    return{
      topField:"",
      bottomField:""
    }
  },

methods: {
    //textFields will take the index from 'block' (this.index) and at that index set the data from topField at index 0 which will then be used in Summary.vue
    replaceAtIndexTop: function() {
      Vue.set(this.textFields[this.index], 0, this.topField);
    },
    //textFields will take the index from 'block' (this.index) and at that index set the data from bottomField at index 0 which will then be used in Summary.vue
    replaceAtIndexBottom: function() {
      Vue.set(this.textFields[this.index], 1, this.bottomField);
    },
    //removeElement will remove data from blocks array and textFields array ager the "x" button is clicked at the given index
    removeElement: function (index) {
      this.blocks.splice(index, 1);
      this.textFields.splice(index, 1);
    },
  },
}
</script>

<style>
.fix-constraints{
  min-width: 250px;
  margin-left: 60px;
  margin-bottom: 30px;
}
.border {
  border: round;
}
.title{
  color: white;
}
span{
  color: white;
}
label {
  color: #222A33;
}
.pad {
  padding-top: 5px;
}

</style>

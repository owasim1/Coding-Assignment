<template>
  <div class="wrapper">
    <nav id="sidebar">
      <ul class="list-unstyled components">
        <li class="fixed-constraints">
          <a href="#" @click="addEducation">Education</a>
        </li>
        <li class="fixed-constraints">
          <a href="#" @click="addProfession">Profession</a>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'Sidebar',
  props: ['blocks', 'textFields',],

  methods: {
    // when the education or profession button is clicked it will push title, fieldOne
    // and fieldTwo into the block array which will be used to create a new block with the data
    // that was pushed. It will also push an id of either 1 (for education) or 0 (for profession).
    addEducation: function () {
        this.blocks.push({title:"Education", field1:"Degree", field2:"Years", example1:"e.g. B.S. Computer Science", example2:"e.g. 2013-2017"});
        this.textFields.push({id:1});
    },
    addProfession: function () {
        this.blocks.push({title:"Profession", field1:"Company", field2:"Years", example1:"e.g. Google", example2:"e.g. 2010-2018"});
        this.textFields.push({id: 0})
    },
  }
}
</script>

<style>
.wrapper {
    display: flex;
}
.fixed-constraints {
  padding-left:55px;
  padding-top: 10px;
  padding-right: 43px;
  padding-bottom: 10px;
  line-height:40px;
}
#sidebar {
    padding-top: 110px;
    width: 200px;
    position: fixed;
    top: 0;
    left: 0;
    min-height: 100vh;
    z-index: 999;
    background: #424B54;;
    color: #fff;
}
.sidebar-header{
  padding-top: 10px;
  padding-left: 40px;
  padding-bottom: 10px;
}
.btnWidth {
  width: 100px;
}
.list-unstyled li:hover{
  background:#5E6B77;
}
.list-unstyled li a {
  display:block;
  text-decoration:none;
  color:#ddd;
}


</style>

<!-- the Summary component is for the bottom part of the page for displaying the data from the block text fields -->
<template>
  <div id="bottom" style="border-top:2px solid black;">
    <table>
      <tr>
        <label>Profession</label>
      </tr>
      <tr v-if="textField.id === 0"  v-for="textField in textFields">
        <td class="fixedWidth">{{ textField[1] }}</td>
        <td>{{ textField[0] }}</td>
      </tr>
    </table>
    <table>
      <tr>
        <label>Education</label>
      </tr>
      <tr v-if="textField.id === 1"  v-for="textField in textFields">
        <td class="fixedWidth">{{ textField[1] }}</td>
        <td>{{ textField[0] }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: 'Summary',
  props: ['textFields'],
}
</script>

<style>

#bottom {
    bottom: 0;
    overflow: auto;
}

table {
  margin-left: 25px;
  margin-top: 10px;
  table-layout: fixed;
}

th,
td {
}
.fixedWidth{
  width: 125px;
}

</style>

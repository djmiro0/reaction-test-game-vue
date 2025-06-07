<template>
  <div class="block">
    CLICK ME!
  </div>
</template>

<script>
export default {
  name: 'Block',
  props: ["delay"]

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.block {
  width: 300px;
  height: 200px;
  text-align: center;
  align-content: center;
  background-color: aquamarine;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  border-radius: 10px;
}
</style>

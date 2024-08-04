<template>
  <div class="background">
    <BookTable></BookTable>
  </div>
</template>

<script>
import BookTable from "./components/BookTable.vue"
export default {
  name: 'App',
  components: {
    BookTable
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;

}
.background {
  width: 100vw;
  height: 100vh;
  overflow: auto;
}
</style>

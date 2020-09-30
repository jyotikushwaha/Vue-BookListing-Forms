<template>
  <form v-on:submit.prevent="bookSubmit(bookData)" class="" action="#" method="post">
    <input v-model="bookData.bookTitle" type="text" name="title" value="" placeholder="Book Title">
    <input v-model="bookData.bookAuthor" type="text" name="author" value="" placeholder="Book Author">
    <label for="finishedReading">Finished Reading</label>
    <input type="checkbox" name="finishedReading" id="finReading" v-model="bookData.finishedReading">
    <label for="borrowed">borrowed</label>
    <input type="radio" name="borrowed" id="own" v-model="bookData.ownership" value="borrowed">
      <label for="bought">bought</label>
      <input type="radio" name="bought" id="own" v-model="bookData.ownership" value="bought">
    <button type="submit" name="button">Add Book</button>
  </form>
</template>

<script>
export default {
  name: "BookForm",
  props: ["books"],
  data() {
    return {
     bookData: {
        bookTitle: "",
        bookAuthor: "",
        finishedReading: false,
        ownership: []
      }
    };
  },
  methods: {
    bookSubmit(bookData) {
      this.$emit("addBook", bookData);
    }
  }
};
</script>

<style>
</style>

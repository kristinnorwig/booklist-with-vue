<template>
  <div id="app" class="inside">
    <LayoutHeader />
    <BookList />
  </div>
</template>

<script>
import LayoutHeader from "./components/LayoutHeader.vue";
import BookList from "./components/BookList.vue";

export default {
  name: "App",
  components: {
    LayoutHeader,
    BookList,
  },
};
</script>

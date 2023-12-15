<template>
  <tr class="table-item__table-row">
    <td>{{ title }}</td>
    <td>{{ isbn }}</td>
    <td>
      <BaseButton :text="getButtonText()" @btn-clicked="bookmarkButtonEvent" />
    </td>
    <td><slot name="actionCol"></slot></td>
  </tr>
</template>

<script>
import BaseButton from "@/components/BaseButton.vue";

export default {
  data() {
    return {
      isBookmarked: false,
    };
  },
  props: {
    title: String,
    isbn: String,
  },
  components: {
    BaseButton,
  },
  methods: {
    bookmarkButtonEvent() {
      this.isBookmarked = !this.isBookmarked;
    },
    getButtonText() {
      if (this.isBookmarked) {
        return "Remove Bookmark";
      } else {
        return "Add Bookmark";
      }
    },
  },
};
</script>

<style scoped>
.table-item__table td {
  padding: 12px 15px;
}
</style>

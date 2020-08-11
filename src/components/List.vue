<template>
  <ul>
    <li v-for="item in items" :key="item.message">{{item.message}}</li>
  </ul>
</template>

<script>
export default {
  name: "v-list",
  props: {
    items: Object,
    default: [],
  },
};
</script>
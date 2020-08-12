<template>
  <div>
    <div v-for="(value,name) in object" :key="name">{{name}} : {{value}}</div>
  </div>
</template>

<script>
export default {
  name: "v-list-object",
  props: {
    object: Object,
    default: {},
  },
};
</script>
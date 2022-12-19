<template>
  <div>
    <div>{{title}}</div>
    <nuxt />
  </div>
</template>

<script>
export default {
  // name: "about",
  middleware: "test",
  asyncData() {
    return { title: "this is the about page" };
  }
};
</script>

<style>
</style>
<template>
  <div>{{slug}}</div>
</template>

<script>
export default {
  validate({ params }) {},
  data() {
    return {
      slug: this.$route.params
    };
  },
  created() {
    console.log(this.$route.params);
  }
};
</script>

<style>
</style>
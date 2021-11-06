<template>
  <div>
    <h1>Oops!</h1>
    <h4>The {{ resource }} you are looking for is not here.</h4>
    <router-link :to="{ name: 'event-list' }"
      >Back to the Home page</router-link
    >
  </div>
</template>

<script>
export default {
  name: "NotFound",

  props: {
    resource: {
      type: String,
      required: true,
    }
  }
};
</script>

<style scoped></style>

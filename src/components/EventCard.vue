<template>
  <router-link
    class="event-link"
    :to="{ name: 'event-show', params: { id: event.id } }"
  >
    <div class="event-card">
      <span class="eyebrow"> @{{ event.time }} on {{ event.date | date }}</span>
      <h4 class="title">{{ event.title }}</h4>
      <BaseIcon name="user">{{ event.attendees.length }} attending</BaseIcon>
    </div>
  </router-link>
</template>

<script>
export default {
  props: {
    event: Object,
  },
};
</script>

<style scoped>
h4 {
  color: #39b982;
}

.event-card {
  padding: 20px;
  margin: 0px 10px 24px 10px;
  transition: all 0.2s linear;
  cursor: pointer;
  box-shadow: 10px 5px 25px rgb(223, 223, 223);
}
.event-card:hover {
  transform: scale(1.01);
  background-color: rgb(240, 255, 251);
}

.event-card > .title {
  margin: 0.2;
}

.event-link {
  color: black;
  text-decoration: none;
}
</style>

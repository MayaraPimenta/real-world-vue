<template>
  <router-link
    class="event-link"
    :to="{ name: 'event-show', params: { id: event.id } }"
  >
    <div class="event-card">
      <span class="eyebrow"> @{{ event.time }} on {{ event.date }}</span>
      <h4 class="title">{{ event.title }}</h4>
      <BaseIcon name="user">{{ event.attendees.length }} attending</BaseIcon>
    </div>
  </router-link>
</template>

<script>
export default {
  data() {
    return {
      event: {
        id: 1,
        title: "Beach Cleanup",
        date: "Tuesday, Aug 19, 2021",
        time: "6:00",
        attendees: [
          { id: "abc123", name: "Adam" },
          { id: "def456", name: "Gregg" },
        ],
      },
    };
  },

  computed: {},
};
</script>

<style scoped>
h4 {
  color: green;
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

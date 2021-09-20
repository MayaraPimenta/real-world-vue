<template>
  <div class="notification-bar" :class="notificationTypeClass">
    <p>{{ notification.message }}</p>
  </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  props: {
    notification: {
      type: Object,
      required: true,
    },
  },

  data() {
    return {
      timeout: null,
    };
  },

  beforeDestroy() {
    clearTimeout(this.timeout);
  },

  mounted() {
    this.timeout = setTimeout(() => this.remove(this.notification), 3000);
  },

  computed: {
    notificationTypeClass() {
      return `text-${this.notification.type}`;
    },
  },

  methods: mapActions("notification", ["remove"]),
};
</script>

<style scoped>
.notification-bar {
  margin: 1em 0 1em;
}

.text-error {
  color: red;
}

.text-success {
  color: #39b982;
}
</style>

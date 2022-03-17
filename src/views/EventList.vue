<template>
  <div>
    <h1>Events Listing</h1>
    <event-card></event-card>
    <base-icon></base-icon>
  </div>
</template>
<script>
import EventCard from "@/components/EventCard";

export default {
  components: {
    EventCard,
  }
}
</script>
<template>
  <div>
    <h1>Events Listing</h1>
    <event-card v-for="(event, index) in events" :key="event.id" :event="event" :position="index+1"></event-card>
  </div>
</template>
<script>
import EventCard from "@/components/EventCard";
import axios from "axios"

export default {
  components: {
    EventCard,
  },

  data() {
    return {
      urlEvent: 'http://localhost:3000/events',
      events: []
    }
  },

  created() {
    axios
        .get(this.urlEvent)
        .then(response => {
          console.log(response.data)
          this.events = response.data
        })
        .catch(error => {
          console.log('there was an error ' + error.response)
        })
  }
}
</script>
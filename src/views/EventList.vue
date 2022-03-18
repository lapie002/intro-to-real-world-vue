<template>
  <div>
    <h1>Events Listing</h1>
    <event-card v-for="(event) in events" :key="event.id" :event="event" :position="event.id"></event-card>
  </div>
</template>
<script>
import EventCard from "@/components/EventCard";
import EventService from "@/services/EventService";

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
    EventService.getEvents()
        .then(response => {
          console.log(response.data)
          this.events = response.data
        })
        .catch(error => {
          console.log('there was an error ' + error.response)
        })

    // axios
    //     .get(this.urlEvent)
    //     .then(response => {
    //       console.log(response.data)
    //       this.events = response.data
    //     })
    //     .catch(error => {
    //       console.log('there was an error ' + error.response)
    //     })
  }
}
</script>
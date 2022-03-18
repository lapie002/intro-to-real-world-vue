<template>
  <div>
    <h1>Showing event #{{ event.id }}</h1>
    <p>{{event.title}}</p>
  </div>

</template>
<script>
import EventService from "@/services/EventService";

export default {
  props: {
    id: {
      type: [String, Number],
      required: true,
    }
  },

  data() {
    return {
      event: {}
    }
  },

  created() {
    EventService.getEventById(this.id)
        .then(response => {
          console.log(response.data)
          this.event = response.data
        })
        .catch(error => {
          console.log('there was an error ' + error.response)
        })
  }
}
</script>
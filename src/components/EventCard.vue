<template>
  <router-link class="event-link" :to="{ name: 'event-show', params: { id: position } }">
    <div class="event-card -shadow">
      <span class="eyebrow">@{{event.time}} on {{event.date}}</span>
      <h4 class="title">{{event.title}}</h4>
      <base-icon name="users">
        <span slot="numberOfAttendee"> {{event.attendees.length}} </span>
        <span slot="attending">attending</span>
        <span>
          <template>
              <h2>Adam Jahr</h2>
              <p>My words.</p>
              <base-icon name="book"></base-icon>
          </template>
        </span>
      </base-icon>
    </div>
  </router-link>
</template>

<script>
import BaseIcon from "@/components/BaseIcon";
export default {
  name: 'EventCard',
  components: {BaseIcon},
  props: {
    event: {
      type: Object,
      required: true
    },
    position: {
      type: [String, Number],
      required: true
    }
  },
  // data() {
  //   return {
  //     event: {
  //       id: 1,
  //       title: 'Beach Cleanup',
  //       date: 'Tues Aug 19, 2018',
  //       time: '6:00',
  //       attendees: [
  //         { id: 'abc123', name: 'Adam Jahr' },
  //         { id: 'def456', name: 'Gregg Pollack' }
  //       ]
  //     }
  //   }
  // }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.event-card {
  padding: 20px;
  margin-bottom: 24px;
  transition: all 0.2s linear;
  cursor: pointer;
}
.event-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2), 0 1px 15px 0 rgba(0, 0, 0, 0.19);
}
.event-card > .title {
  margin: 0;
}
.event-link {
  color: black;
  text-decoration: none;
  font-weight: 100;
}
</style>

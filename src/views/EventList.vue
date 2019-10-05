<template>
  <div class="List">
    <h1>Event List</h1>
    <EventCard v-for="event in events" :key="event.id" :event="event" />
    <!-- EventCard:EventCard -->
  </div>
</template>
<script>
import EventCard from '@/components/EventCard.vue'
import EventService from '@/services/EventService.js'
export default {
  components: {
    EventCard
  },
  data() {
    return {
      events: []
    }
  },
  created() {
    EventService.getEvents()
      .then(response => {
        this.events = response.data
      })
      .catch(error => {
        console.log('There Was An error')
      })
  }
}
</script>

<template>
  <h1>Event For Good</h1>
  <!-- <div class="home"> -->
  <div class="events">
    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>
  <div class="category">
    <!-- <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" /> -->
    <Categories v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue"
import EventCard from "@/components/EventCard.vue"
import Categories from "@/components/Categories.vue"
export default {
  name: "EventListView",
  components: {
    EventCard, //register
    Categories,
  },
  data() {
    return {
      events: [
        {
          id: 5928101,
          category: "animal welfare",
          title: "Cat Adoption Day",
          description: "Find your new feline friend at this event.",
          location: "Meow Town",
          date: "January 28, 2022",
          time: "12:00",
          petsAllowed: true,
          organizer: "Kat Laydee",
        },
        {
          id: 4582797,
          category: "food",
          title: "Community Gardening",
          description: "Join us as we tend to the community edible plants.",
          location: "Flora City",
          date: "March 14, 2022",
          time: "10:00",
          petsAllowed: true,
          organizer: "Fern Pollin",
        },
        {
          id: 8419988,
          category: "sustainability",
          title: "Beach Cleanup",
          description: "Help pick up trash along the shore.",
          location: "Playa Del Carmen",
          date: "July 22, 2022",
          time: "11:00",
          petsAllowed: false,
          organizer: "Carey Wales",
        },
      ],
    }
  },
}
</script>
<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.category {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: right;
}
</style>

<template>
  <h1>Events For Good</h1>
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
// import axios from "axios"
import EventService from "../services/EventService.js"
export default {
  name: "EventListView",
  components: {
    EventCard, //register
    Categories,
  },
  data() {
    return {
      events: null,
    }
  },
  created() {
    //get event
    // axios
    //   .get("http://localhost:3004/events")
    EventService.getEvents()
      .then((response) => {
        this.events = response.data
      })
      .catch((error) => {
        console.log(error)
      })
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

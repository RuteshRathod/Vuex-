<template>
  <div>
    <h1>Create an Event{{ user.name }}</h1>
    <p>This event is created by {{ user.id }}</p>
    <p>There are:- {{ catLength }} categories</p>
    <p>{{ getEventById }}</p>
    <ul>
      <li v-for="cat in categories" :key="cat">{{ cat }}</li>
    </ul>
  </div>
</template>

<script>
import { mapState, mapGetters } from 'vuex'
export default {
  computed: {
    catLength() {
      return this.$store.getters.catLength
    },
    ...mapGetters(['getEventById']),
    ...mapState(['user', 'categories'])
  }
}
</script>

<style lang="scss" scoped></style>

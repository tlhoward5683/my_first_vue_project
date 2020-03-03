<template>
  <div class="green">
    <Users v-bind:users="usersData" v-bind:rowColor="rowColor" />
    <button v-on:click="highlight()" class="btn">Click Me</button>
  </div>
</template>

<script>
import Users from '../components/Users'

export default {
  name: 'Green',
  components: {
    Users
  },
  props: ["usersData"],
  data() {
    return {
        rowColor: 'whiteRow'
    }
  },
  methods: {
    highlight: function () {
      if (this.rowColor === 'whiteRow') {
        this.rowColor = 'greenRow'
      } else {
        this.rowColor = 'whiteRow'
      }
    }
  }
}
</script>

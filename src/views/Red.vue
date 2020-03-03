<template>
  <div class="red">
    <Users v-bind:users="usersData" v-bind:rowColor="rowColor"   />
    <button v-on:click="highlight()" class="btn">Click Me</button>
  </div>
</template>

<script>
// @ is an alias to /src
import Users from '../components/Users'

export default {
  name: 'Red',
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
        this.rowColor = 'redRow'
      } else {
        this.rowColor = 'whiteRow'
      }
    }
  }
}
</script>

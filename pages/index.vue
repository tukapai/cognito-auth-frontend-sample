<template>
  <div>
    <p>{{ $auth.user }}</p>
    <button @click.prevent="$auth.logout()">Logout</button>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage'
})
</script>

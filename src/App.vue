<template>
  <div style="margin-top: 10px">
    <User ref="user" @syncpermissions='syncPermissions' /><Message ref="message" v-bind:permissions="permissions" />
  </div>
</template>

<script>
import User from './components/User.vue'
import Message from './components/Message.vue'

export default {
  name: 'app',
  data () {
    return {
      permissions: []
    }
  },
  components: {
    User,
    Message
  },
  mounted: function () {
  },
  methods: {
    syncPermissions (permissions) {
      this.permissions = permissions
    }
  }
}

</script>

<style>
</style>

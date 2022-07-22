<template>
  <div class="ui card">
    <form class="ui form">
      <div class="field">
        <div class="ui left icon fluid input">
          <input ref="txtId" type="text" placeholder="Input user id...">
          <i class="user icon"></i>
        </div>
      </div>
      <button id="btnCheck" v-on:click="(event) => check(this.$refs.txtId.value, event)"
        class="ui primary fluid submit button" type="submit">CHECK</button>
      <div class="ui error message"></div>
    </form>
  </div>
</template>

<script>
import Vue from 'vue'
import axios from 'axios'
import qs from 'qs'

Vue.prototype.$axios = axios
Vue.prototype.qs = qs

export default {
  data () {
    return {
    }
  },
  mounted () {
  },
  methods: {
    check (userId, event) {
      if (event) {
        event.preventDefault()
      }
      this.$axios({
        method: 'get',
        url: 'http://localhost:8080/user/' + userId
      }).then((response) => {
        this.$emit('syncpermissions', response.data.permissions)
      }).catch((error) => {
        console.log(error)
      })
    }
  }
}
</script>

<style>
.ui.card {
  margin: 10px;
  padding: 10px;
}
</style>

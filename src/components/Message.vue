<template>
  <div ref="listPermissions" class="ui card relaxed divided list">
    <div v-for="(permission, index) in permissions" v-bind:key="index" class="item">
      <i class="large middle aligned icon"></i>
      <div class="content">
        <a class="header">{{ permission.department.name }}</a>
        <div class="description">{{ permission.permissionType }}</div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Message',
  props: ['permissions'],
  watch: {
    permissions: function (newValue, oldValue) {
      console.log(newValue)
      console.log(oldValue)
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

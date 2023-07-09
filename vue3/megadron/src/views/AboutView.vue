<template>
  <div class="about">
    <h1>This is an about page</h1>
    {{ appName }}
  </div>
</template>

<script>

export default {
  name: 'About',
  data(){
    const appName=process.env.VUE_APP_NAME;
    return {
      appName
    }
  }
}
</script>
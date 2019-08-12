<template>
  <div class="home">
    <weButton type="primary">submit</weButton>
    <weButton type="warning">submit</weButton>
    <weButton type="default" loading>submit</weButton>
    <weButton type="primary" disabled>submit</weButton>
    <weButton type="primary" loading>submit</weButton>
  </div>
</template>

<script>
// @ is an alias to /src
import weButton from '@/components/weButton.vue'

export default {
  name: 'home',
  components: {
    weButton
  }
}
</script>

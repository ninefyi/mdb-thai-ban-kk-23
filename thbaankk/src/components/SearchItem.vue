<template>
  <div>
    <i>
      <p>My search query is: {{ message }}</p>
      <input v-model="message" placeholder="edit me" />
    </i>
    <div class="details"></div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      message: '',
    }
  },
}
</script>
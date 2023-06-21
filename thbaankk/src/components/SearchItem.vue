<template>
  <div>
    <p>คำที่ค้นหา: {{ message }}</p>
    <p><input v-model="message" placeholder="ใส่คำค้นหา ภาษาไทย" />&nbsp;
      <button @click="fetchData">ค้นเลยจ้า!!!</button>
    </p>
  </div>
  <div class="container-fluid">
    <div class="row">
      <com-singer v-for="(card, idx) in cards" :key="idx" v-bind:card="card"></com-singer>
    </div>
  </div>
</template>
<script>
import ListItem from './ListItem.vue'
export default {
  data() {
    return {
      cards: [],
      message: '',
    }
  },
  methods: {
    fetchData() {
      fetch('https://ap-southeast-1.aws.data.mongodb-api.com/app/singer-jllwn/endpoint/search', {
        method: "POST",
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({ "query": this.message })
      })
        .then((response) => {
          response.json().then((data) => {
            this.cards = data.result;
          });
        })
        .catch((err) => {
          console.error(err);
        });
    },
  },
  components: {
    comSinger: ListItem,
  }
}
</script>


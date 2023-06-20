<template>
  <div>
    <i>
      <p>My search query is: {{ message }}</p>
      <input v-model="message" placeholder="enter your query" />&nbsp;
      <button @click="fetchData">Query Please!</button>
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
            console.log(data);
          });
        })
        .catch((err) => {
          console.error(err);
        });
    },
  },
}
</script>
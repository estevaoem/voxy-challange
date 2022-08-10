<template>
  <div>
    <h1 class="title">{{ msg }}</h1>
    <p>Enter a sentence bellow and hit enter to count the words</p>
    <form v-on:submit.prevent="countWords">
      <input
        type="text"
        placeholder="Click here to enter a sentence"
        name="formData"
        @keypress:enter="countWords(words)"
      />
    </form>
  </div>
</template>

<script>
export default {
  name: "PageContents",
  props: {
    msg: String,
  },
  methods: {
    countWords(event) {
      const sentence = event.target.elements.formData.value;
      const words = sentence.split(" ");
      const wordCount = words.length;

      if (words.length === 1 && words[0] === "") {
        console.log("Form can't be empty");
      } else {
        console.log(`${wordCount} word(s) registered`);
      }
    },
  },
};
</script>

<style scoped>
.title {
  padding-top: 4rem;
  padding-bottom: 1rem;
}

input {
  width: 25rem;
  height: 2rem;
}
</style>

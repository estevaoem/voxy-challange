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
  <WordCounter :count="count" />
</template>

<script>
import WordCounter from "./WordCounter.vue";

export default {
  name: "PageContents",
  components: {
    WordCounter,
  },
  data() {
    return {
      count: -1,
      symbols: new RegExp("^.*[-!$@%^&*()_+|~=`{}[\\]:\";'<>?,.\\/]+.*$"),
    };
  },
  props: {
    msg: String,
  },
  methods: {
    countWords(event) {
      const sentence = event.target.elements.formData.value;
      const wordCandidates = sentence.split(" ");

      const words = [];

      for (const word of wordCandidates) {
        if (this.symbols.test(word)) {
          for (const letter of word) {
            if (!this.symbols.test(letter)) {
              words.push(word);
              break;
            }
          }
          continue;
        }
        if (word === "") {
          continue;
        }
        words.push(word);
      }

      this.count = words.length;
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

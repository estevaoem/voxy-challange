<template>
  <div class="word-count">
    <div class="count-positive" v-if="count > 0">
      <span>
        <span class="count-number">{{ count }}</span>
        <span> word<span v-if="count > 1">s</span> registered</span>
      </span>
    </div>
    <div class="count-empy" v-if="count === 0">
      <span> Either the form contain invalid words or is empty </span>
    </div>
  </div>
</template>

<script>
export default {
  name: "WordCounter",
  props: {
    count: Number,
  },
};
</script>

<style scoped>
.word-count {
  padding-top: 1rem;
}

.count-number {
  color: green;
  font-weight: bold;
}

.count-empy {
  color: red;
  font-weight: bold;
}
</style>

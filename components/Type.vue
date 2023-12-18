<template>
  <div class="flex bg-neutral-300">
    <div class="text-6xl font-medium text-black">
      I am a&nbsp;<span class="changing-word text-red-500">{{ currentText }}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    wordOptions: {
      type: Array,
      default: () => ['Coder', 'Writer', 'Geek'],
    },
  },
  data() {
    return {
      currentWordIndex: 0,
      currentText: '',
    };
  },
  methods: {
    async typeText(word) {
      let index = 0;

      while (index <= word.length) {
        this.currentText = word.substring(0, index);
        index++;
        await this.sleep(100); // Adjust the speed of typing
      }

      await this.sleep(2000); // Pause before the next word
    },
    async deleteText(word) {
      let index = word.length;

      while (index >= 0) {
        this.currentText = word.substring(0, index);
        index--;
        await this.sleep(50); // Adjust the speed of backspacing
      }
    },
    async changeWord() {
      for (;;) {
        for (const word of this.wordOptions) {
          await this.typeText(word);
          await this.deleteText(word);
        }
      }
    },
    sleep(ms) {
      return new Promise(resolve => setTimeout(resolve, ms));
    },
  },
  mounted() {
    this.changeWord();
  },
};
</script>

<style scoped>
.text-container {
  display: flex;
  align-items: center;
}

.changing-word {
  display: inline-block;
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out forwards;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>

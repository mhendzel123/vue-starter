<template>
  <div>
    <label>Zaloguj siÄ™ e-mailem</label>
    <input type="email" v-model="email" />
    <button @click="enter()">{{ buttonLabel }}</button>
  </div>
</template>

<script>
export default {
  props: ["buttonLabel"],
  data() {
    return {
      email: ""
    };
  },
  methods: {
    enter() {
      this.$emit("login", this.email);
    }
  },
  //     mounted() {
  // 	if (!this.buttonLabel) {
  // 		this.buttonLabel = 'Zaloguj sie';
  // 	}
  // },

  computed: {
    buttonLabelToDisplay() {
      return this.buttonLabel || "Zaloguj siê";
    }
  }
}
</script>
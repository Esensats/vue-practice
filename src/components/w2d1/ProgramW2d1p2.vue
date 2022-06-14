<template>
  <div class="program">
    <p class="program__paragraph">Введите <b>m</b>:</p>
    <input
      type="text"
      class="program__input"
      :value="m"
      @input="onInput($event)"
    />
    <p class="program__paragraph">N = {{ n }}</p>
  </div>
</template>

<script>
export default {
  name: "ProgramW2d1p2",
  data() {
    return {
      m: null,
      n: null,
    };
  },
  methods: {
    onInput($event) {
      this.m = Number($event.target.value);
      this.n = Math.pow(this.m, 2) + (2.8 * Math.abs(this.m)) + 0.55;
    },
  },
};
</script>

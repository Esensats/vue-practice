<template>
  <form class="program" @submit="onSubmit($event)">
    <p class="program__paragraph">Введите <b>N</b>:</p>
    <input type="text" class="program__input" @input="onInputN($event)" />
    <br />
    <input type="submit" class="btn" value="Готово" />
    <p class="program__paragraph">K = {{ k }}</p>
    <p class="program__paragraph">3K = {{ k3 }}</p>
  </form>
</template>

<script>
export default {
  name: "ProgramW2d3p1",
  data() {
    return {
      n: null,
      k: null,
      k3: null
    };
  },
  methods: {
    onInputN($event) {
      this.n = Number($event.target.value);
    },
    onSubmit($event) {
      $event.preventDefault();
      // this.k = 1;
      // while (3 * this.k < this.n) {
      //   this.k++;
      // }
      this.k = Math.floor((this.n / 3)) + 1;
      this.k3 = this.k * 3;
    },
  },
};
</script>

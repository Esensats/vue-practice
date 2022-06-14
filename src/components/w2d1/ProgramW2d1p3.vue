<template>
  <form class="program" @submit="onSubmit($event)">
    <p class="program__paragraph">Введите массу <b>m</b>:</p>
    <input
      type="text"
      class="program__input"
      :value="m"
      @input="onInputM($event)"
    />
    <p class="program__paragraph">Введите высоту <b>h</b>:</p>
    <input
      type="text"
      class="program__input"
      :value="h"
      @input="onInputH($event)"
    />
    <p class="program__paragraph">Введите скорость <b>v</b>:</p>
    <input
      type="text"
      class="program__input"
      :value="v"
      @input="onInputV($event)"
    />
    <br>
    <input type="submit" class="btn" value="Готово" />
    <p class="program__paragraph">E = {{ e }}</p>
    <p class="program__paragraph">P = {{ p }}</p>
  </form>
</template>

<script>
export default {
  name: "ProgramW2d1p3",
  data() {
    return {
      m: null,
      h: null,
      v: null,
      e: null, //result
      p: null, //result
    };
  },
  methods: {
    onInputM($event) {
      this.m = Number($event.target.value);
    },
    onInputH($event) {
      this.h = Number($event.target.value);
    },
    onInputV($event) {
      this.v = Number($event.target.value);
    },
    onSubmit($event) {
      $event.preventDefault();
      this.e = (this.m * Math.pow(this.v, 2)) / 2;
      this.p = this.m * this.h * 9.8;
    }
  },
};
</script>

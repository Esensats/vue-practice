<template>
  <form class="program" @submit="onSubmit($event)">
    <p class="program__paragraph">Введите <b>X</b>:</p>
    <input type="text" class="program__input" @input="onInputX($event)" />
    <p class="program__paragraph">Введите <b>Y</b>:</p>
    <input type="text" class="program__input" @input="onInputY($event)" />
    <p class="program__paragraph">Введите радиус <b>R</b>:</p>
    <input type="text" class="program__input" @input="onInputR($event)" />
    <br />
    <input type="submit" class="btn" value="Готово" />
    <p class="program__paragraph">{{ msg }}</p>
  </form>
</template>

<script>
export default {
  name: "ProgramW2d2p2",
  data() {
    return {
      x: null,
      y: null,
      r: null,
      msg: "",
    };
  },
  methods: {
    onInputX($event) {
      this.x = Number($event.target.value);
    },
    onInputY($event) {
      this.y = Number($event.target.value);
    },
    onInputR($event) {
      this.r = Number($event.target.value);
    },
    onSubmit($event) {
      $event.preventDefault();
      if (this.x * this.x + this.y * this.y < this.r * this.r) this.msg = "Данная точка лежит внутри окружности радиуса " + this.r;
      else this.msg = "Данная точка НЕ лежит внутри окружности радиуса " + this.r;
    },
  },
};
</script>

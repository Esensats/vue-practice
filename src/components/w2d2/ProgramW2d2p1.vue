<template>
  <form class="program" @submit="onSubmit($event)">
    <p class="program__paragraph">Введите <b>X</b>:</p>
    <input
      type="text"
      class="program__input"
      @input="onInputX($event)"
    />
    <p class="program__paragraph">Введите <b>Y</b>:</p>
    <input
      type="text"
      class="program__input"
      @input="onInputY($event)"
    />
    <p class="program__paragraph">Введите <b>Z</b>:</p>
    <input
      type="text"
      class="program__input"
      @input="onInputZ($event)"
    />
    <br />
    <input type="submit" class="btn" value="Готово" />
    <p class="program__paragraph">X = {{ x1 }}</p>
    <p class="program__paragraph">Y = {{ y1 }}</p>
    <p class="program__paragraph">Z = {{ z1 }}</p>
  </form>
</template>

<script>
export default {
  name: "ProgramW2d2p1",
  data() {
    return {
      x: null,
      y: null,
      z: null,
      x1: null,
      y1: null,
      z1: null,
    };
  },
  methods: {
    onInputX($event) {
      this.x = Number($event.target.value);
    },
    onInputY($event) {
      this.y = Number($event.target.value);
    },
    onInputZ($event) {
      this.z = Number($event.target.value);
    },
    onSubmit($event) {
      $event.preventDefault();
      this.x1 = this.x;
      this.y1 = this.y;
      this.z1 = this.z;
      if (this.z1 > this.x1) {
        [this.x1, this.z1] = [this.z1, this.x1];
      }
      if (this.z1 > this.y1) {
        [this.y1, this.z1] = [this.z1, this.y1];
      }
      if (this.y1 > this.x1) {
        [this.x1, this.y1] = [this.y1, this.x1];
      }
    },
  },
};
</script>

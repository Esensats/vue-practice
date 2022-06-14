<template>
  <div class="HomeView">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <div class="container">
      <div class="task" v-for="task in tasks" :key="task.slug">
        <h3 class="task__name">{{ task.name }}</h3>
        <div
          class="program"
          v-for="program in task.programs"
          :key="program.slug"
        >
          <h4 class="program__name">
            <router-link :to="'/programs/' + task.slug + '/'+ program.slug">
              {{ program.name }}
            </router-link>
          </h4>
          <p class="program__overview">{{ program.overview }}</p>
        </div>
        <!-- <hr /> -->
      </div>
      <!-- <button class="btn btn-block">Hello</button> -->
    </div>
  </div>
</template>

<script>
import json from "@/data/data.json";

export default {
  name: "HomeView",
  components: {},
  data() {
    return {
      tasks: json.tasks,
    };
  },
};
</script>

<style lang="scss">
@use "@/styles";
.HomeView {
  .task {
    border-bottom: 1px solid styles.$colorSecondaryLight;
    padding-bottom: .5rem;
    margin-bottom: .5rem;

    &__name {
      margin-bottom: .1rem;
    }
  }
  .program {
    margin-left: .4rem;

    &__name {
      padding-top: .4rem;
      padding-bottom: .25rem;

      a {
        color: styles.$colorPrimaryDarker;
        text-decoration: none;
        font-weight: normal;
        
        &:hover {
          color: styles.$colorSecondary;
          border-bottom: 1px solid styles.$colorSecondary;
        }
      }
    }
    &__overview {
      margin-left: .3rem;
      padding: .25rem .25rem .25rem .35rem;
      border-left: 2px solid styles.$colorPrimaryLight;
    }
  }
}
</style>

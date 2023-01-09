<template>
  <div class="card">
    <h1>{{ title }}</h1>



    <button class="btn" @click="navigatevfhfnfytw">Открыть пользователей</button>
  </div>
</template>

<script lang="ts">
import {defineComponent} from "vue";
import {useRouter} from "vue-router";

export default defineComponent({
  setup() {
    const router = useRouter();
    return {
      title: "Как Vue работает с TypeScript?",
      navigate: () => router.push('/users')
    }
  }

  // data() {
  //   return {
  //     title: "Как Vue работает с TypeScript?"
  //   }
  // }
})

</script>
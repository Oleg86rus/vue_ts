<template>
  <div class="card">
    <h1>Пользователи</h1>

    <p style="color: red;" v-if="error">{{error.message}}</p>

    <Suspense v-else>
      <template #default>
        <UserList/>
      </template>
      <template #fallback>
        <p>Loading</p>
      </template>
    </Suspense>
  </div>
</template>

<script lang="ts">
import {defineComponent, onErrorCaptured, ref} from "vue";
import UserList from "../components/UserList.vue";

export default defineComponent({
  setup() {
    const error = ref<null | unknown>(null)
    console.log()
    onErrorCaptured(e => {
      error.value = e
      return true
    })
    console.log({error})
    return {error}
  },
  components: {UserList}
})

</script>

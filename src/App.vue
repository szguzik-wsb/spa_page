<script setup>
import {RouterLink, RouterView} from 'vue-router'
import TopBarComponents from "@/components/TopBarComponents.vue";

</script>
<template>
  <div>
    <TopBarComponents/>
  </div>
  <div>
    <!--zmiana-->
    <RouterView/>
    <!--koniec zmiany-->
    <footer class="footer">
      <div class="container">
        <div class="content has-text-centered">
          <p>
            <strong>WSB</strong>. Projekt do zajęć
          </p>
        </div>
      </div>
    </footer>
  </div>
</template>

<style scoped>

</style>

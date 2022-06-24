<template>
  <div class="container-block">
    <hudcontainer></hudcontainer>
  </div>
</template>

<script>
import HUDHumanCont from "./components/HUDHumanCont.vue";

export default {
  components: {
    hudcontainer: HUDHumanCont,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
</style>

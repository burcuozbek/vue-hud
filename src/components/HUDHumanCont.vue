<template>
  <div
    class="
      hud-human-container
      d-flex
      flex-row
      justify-content-start
      align-items-center
    "
  >
    <ul class="hud-human">
      <span class="control">
        <i
          class="fas fa-angle-double-right"
          :class="{ rotate: rotateArrow }"
          @click="showNav"
        ></i>
      </span>
      <TransitionGroup name="fade">
        <li class="healt" v-show="!showBar" key="1">
          <i class="fa-solid fa-heart-pulse"></i>
        </li>
        <li class="hunger" v-show="!showBar" key="2">
          <i class="fa-solid fa-burger"></i>
        </li>

        <li class="thirst" v-show="!showBar" key="3">
          <i class="fa-solid fa-droplet"></i>
        </li>
        <li class="stamina" v-show="!showBar" key="4">
          <i class="fa-solid fa-person-running"></i>
        </li>
        <li class="armor" v-show="!showBar" key="5">
          <i class="fa-solid fa-shield-halved"></i>
        </li>
        <li class="oxy" v-show="!showBar" key="6">
          <i class="fa-solid fa-lungs"></i>
        </li>
        <li class="durability" v-show="!showBar" key="7">
          <i class="fa-solid fa-hand-fist"></i>
        </li>
      </TransitionGroup>
    </ul>
    <ul>
      <TransitionGroup name="fade">
        <li v-show="!showBar" class="protein" key="8">
          <i class="fa-solid fa-burger"></i>
        </li>
        <li v-show="!showBar" class="oil" key="9">
          <i class="fa-solid fa-droplet"></i>
        </li>
        <li v-show="!showBar" class="carbohydrate" key="10">
          <i class="fa-solid fa-burger"></i></li
      ></TransitionGroup>
    </ul>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      showBar: false,
      rotateArrow: false,
    };
  },
  methods: {
    showNav() {
      this.showBar = !this.showBar;
      this.rotateArrow = !this.rotateArrow;
    },
  },
};
</script>


<style scoped>
ul {
  height: 460px;
  list-style-type: none;
  margin-left: 10px;
  padding: 0;
}
li {
  height: 56px;
  width: 67px;
  margin-bottom: 5px;
  clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 75% 100%, 25% 100%, 0% 50%);
  display: flex;
  align-items: center;
  justify-content: center;
}
li.healt {
  background: #93000e;
}
li.hunger {
  background: #db7500;
}
li.thirst {
  background: #00a4e1;
}
li.stamina {
  background: #ff3506;
}
li.armor {
  background: #414141;
}
li.oxy {
  background: #0d509c;
}
li.durability {
  background: #437512;
}

.hud-human-container {
  height: 100vh;
}
.hud-human-container ul.hud-human li i {
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 22px;
}
.healt i {
  color: white;
}
.stamina i {
  color: white;
}
.armor i {
  color: white;
}
.oxy i {
  color: white;
}
.durability i {
  color: white;
}
.control {
  font-size: 25px;
  margin-left: 25px;
}

.rotate {
  transform: rotateZ(-180deg);
}
.protein {
  height: 39px;
  width: 50px;
  background: #93000e;
  position: relative;
  left: -39%;
  top: 86px;
}
.oil {
  height: 39px;
  width: 50px;
  background: #a78e16;
  position: relative;
  left: -38%;
  top: 83px;
}
.carbohydrate {
  height: 39px;
  width: 50px;
  background: #995d17;
  position: relative;
  left: 42%;
  top: 18px;
}
/* TRANSITIONS */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>

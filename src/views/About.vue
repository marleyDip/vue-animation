<template>
  <div class="about">
    <transition
      appear
      name="fade"
      @before-enter="beforeEnter"
      @enter="enter"
      @after-enter="afterEnter"
      @before-leave="beforeLeave"
      @leave="leave"
      @after-leave="afterLeave"
    >
      <h1 v-if="showTitle">About</h1>
    </transition>

    <p>
      The Transition Component....But luckily Vue provides us with the built-in
      Transition component in cases where we want to animate an element as it is
      removed from, or added to, our application with v-if or v-show, because
      that would be hard to do with plain CSS animation.
    </p>
    <p>
      As an element inside the Transition component is added, we can use these
      first three classes to animate that transition:
      v-enter-from..v-enter-active..v-enter-to And as an element is removed
      inside the Transition component, we can use the next three classes:
      v-leave-from..v-leave-active..v-leave-to
    </p>
    <p>
      Transition Between Elements....The Transition component can also be used
      to switch between several elements, as long as we make sure that only one
      element is shown at a time with the use of v-if and v-else-if:
    </p>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const showTitle = ref(true);

    //Enter
    const beforeEnter = (el) => {
      console.log("beforeEnter", el);
    };
    const enter = (el) => {
      console.log("enter", el);
    };
    const afterEnter = (el) => {
      el.style.color = "green";
      console.log("afterEnter", el);

      setTimeout(() => (showTitle.value = false), 2000);
    };
    //Leave
    const beforeLeave = (el) => {
      el.style.color = "pink";
      console.log("beforeLeave", el);
    };
    const leave = (el) => {
      console.log("leave", el);
    };
    const afterLeave = (el) => {
      console.log("afterLeave", el);
    };

    return {
      beforeEnter,
      enter,
      afterEnter,
      beforeLeave,
      leave,
      afterLeave,
      showTitle,
    };
  },
};
</script>

<style>
.about {
  max-width: 600px;
  margin: 20px auto;
}
.about p {
  text-align: justify;
  margin-bottom: 30px;
}

.fade-enter-from {
  opacity: 0;
}
/* .fade-enter-to {
  opacity: 1;
  rotate: 360deg;
} */
.fade-enter-active {
  transition: opacity 0.3s ease;
}
.fade-leave-to {
  opacity: 0;
}
.fade-leave-active {
  transition: opacity 0.3s ease;
}
</style>
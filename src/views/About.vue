<template>
  <div class="about">
    <h1>About</h1>

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
export default {
  setup() {},
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
</style>
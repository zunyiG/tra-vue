<template>
    <transition
    name="custom-class"
    :enter-class="$style.enter"
    :leave-to-class="$style.leave"
    :enter-active-class="$style.enterActive"
    :leave-active-class="$style.leaveActive"
    >
      <slot></slot>
    </transition>
</template>

<script>

export default {
  name: 'Fade'
}
</script>

<style module>

  .enter, .leave {
    opacity: 0;
  }

  .enterActive, .leaveActive {
    transition: opacity .5s;
  }

</style>

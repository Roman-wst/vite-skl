<script setup>
  const props = defineProps({
    icon: { type: String, required: false, default: "" },
    label: { type: String, required: false, default: "" },
    btnStyle: { type: String, required: false, default: "" },
    to: { type: String, required: false, default: "" },
  })

</script>

<template>
  <button
    :class="`btn btn-${btnStyle}`"
    @click="clickHandler"
  >
    <span
      v-if="icon"
      :class="`icon ${icon}`"
    />
    <span>{{ label }}</span>
  </button>
</template>


<style scoped lang="scss">
.btn {
  font-family: $font-medium;
  display: inline-flex;
  align-items: center;
  padding: rem(16) rem(24);
  border-radius: rem(10);
  border: 1px solid transparent;
  transition: background-color 0.2s linear, border-color 0.2s linear;
  white-space: nowrap;
  cursor: pointer;

  &:disabled {
    pointer-events: none;
  }

  & .icon {
    font-size: rem(21);
    margin-right: rem(8);
  }

  &:disabled {
    opacity: 0.3;
  }

  @media (hover: hover) {
    &:hover {
      background-color: $btn-bg-hover;
      color: $text-color;
    }
  }

  &:focus {
    background-color: $btn-bg-hover;
    color: $text-color;
  }

  &:active {
    background-color: $btn-bg-active;
    color: $text-color;
  }
}

.btn-accent {
  background-color: $btn-bg-accent;
  color: $text-color;
}

.btn-primary {
  background-color: $btn-bg-primary;
  color: #fff;
}

</style>

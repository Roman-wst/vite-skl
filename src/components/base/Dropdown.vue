<script setup>
import { ref } from 'vue'
const props = defineProps({
    isLeft: { type: Boolean, required: false, default: true },
    items: Array,
    modelValue: String 
  });

const emit = defineEmits(['update:modelValue'])
const isOpen = ref(false) 
const select = (item) => {
  emit('update:modelValue', item)
  isOpen.value = false
}


</script>

<template>
  <div
    class="dropdown"
    :class="{
      'is-open': isOpen,
      'is-left': isLeft,
    }"
  >
    <div
      class="dropdown__toggle"
      @click="isOpen = !isOpen"
    >
      {{ modelValue }}
    </div>

    <span class="icon icon-arrow-select"></span>

    <div class="dropdown__menu">
      <ul class="dropdown__list">
        <li 
          v-for="item in items"
          :key="item"
          class="dropdown__list-item"
          @click="select(item)"
        >
          {{ item }}
        </li>
      </ul>
    </div>
  </div>
</template>


<style scoped lang="scss">
.dropdown {
  position: relative;
  display: inline-block;
  width: 100%;
  outline: none;

  .icon {
    font-size: rem(6);
    color: #55555C;
    position: absolute;
    right: rem(26);
    top: 50%;
    margin-top: rem(-3);
    transition: transform 0.2s linear;
  }

  &__input:focus + .icon {
    color: $text-color;
  } 

  &__toggle { 
    padding: rem(17) rem(56) rem(17) rem(24);
    border-radius: rem(10);
    border: 1px solid #D3D3DE;
    outline: none;
    cursor: pointer;
  }

  &__menu {
    position: absolute;
    top: 100%;
    z-index: 99;
    min-width: 100%;
    opacity: 0;
    visibility: hidden;
    transition: opacity 0.2s linear, transform 0.2s linear,
      visibility 0s linear 0.2s;
  }

  &.is-left &__menu {
    left: 0;
  }

  &.is-open {
    border-color: $text-color;

    .icon {
      transform: scale(-1);
    }
  }

  &.is-open &__menu {
    opacity: 1;
    visibility: visible;
    transition: opacity 0.2s linear, transform 0.2s linear,
      visibility 0s linear 0s;
  }

  &__menu {
    margin: rem(4) 0;
    padding: rem(6);
    max-height: rem(250);
    background-color: #F1F4FD;
    border-radius: rem(10);
    overflow-y: auto;
    box-shadow: 0 rem(5) rem(40) rgba(#000, .1);
  }

  &__list {
    list-style: none;
  }

  &__list-item + &__list-item { 
    margin-top: 1px;
  }

  &__list-item {
    @include font(12, 16);
    display: block;
    padding: rem(10) rem(16);
    border-radius: rem(8);
    background-color: #E4E4EE;
    cursor: pointer;
  }

  @media (hover: hover) {
    &__list-item:hover {
      background-color: #D3D3DE;
    }
    
    &__list-item:active {
      color: #93939B; 
      background-color: #E4E4EE;
    }
  }
}
</style>

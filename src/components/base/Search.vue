<script setup>
  const props = defineProps({
    placeholder: { type: String, required: false, default: "" },
  })
</script>

<template>
  <div class="search">
    <input
      name="name"
      type="text"
      :placeholder="placeholder"
      class="search__input"
    />
    <span class="icon icon-search"></span>
  </div>
</template>

<style scoped lang="scss">
.search {
  position: relative;
  align-items: center;

  @include media-min($screen-md-min) {
    width: rem(300);
  }

  &__input {
    width: 100%;
    padding: rem(17) rem(56) rem(17) rem(24);
    border-radius: rem(10);
    border: 1px solid #D3D3DE;
    outline: none;

    &:focus {
      border-color: $text-color;
    }
  }

  .icon {
    font-size: rem(20);
    color: #55555C;
    position: absolute;
    right: rem(26);
    top: 50%;
    transform: translateY(-50%);
  }

  &__input:focus + .icon {
    color: $text-color;
  } 
}
</style>

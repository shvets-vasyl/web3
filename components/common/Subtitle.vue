<template>
  <span class="subtitle">
    <svg
      class="desk"
      viewBox="0 0 9 52"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M9 0.999998L1 0.999999L1.00001 51L9 51"
        stroke="#D5F430"
        stroke-width="1.5"
      />
    </svg>

    <svg
      class="mob"
      viewBox="0 0 7 34"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path d="M7 1L1 1L1 33L7 33" stroke="#D5F430" stroke-width="1.5" />
    </svg>

    <slot />

    <svg
      class="desk"
      viewBox="0 0 9 52"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M4.37114e-06 1L8 1L7.99999 51L4.37114e-06 51"
        stroke="#D5F430"
        stroke-width="1.5"
      />
    </svg>

    <svg
      class="mob"
      viewBox="0 0 7 34"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M2.79753e-06 1L6 1L6 33L3.27835e-06 33"
        stroke="#D5F430"
        stroke-width="1.5"
      />
    </svg>
  </span>
</template>
<script setup lang="ts"></script>
<style scoped lang="scss">
.subtitle {
  display: inline-flex;
  align-items: center;
  gap: 1.5rem;

  @include mobile {
    gap: 0.625rem;
  }
}
.subtitle svg {
  width: 0.5625rem;
  @include mobile {
    width: 0.4375rem;
  }
}
</style>

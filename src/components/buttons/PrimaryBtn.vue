<template>
  <div class="cursor-pointer">
    <button type="button" @click="emitClickEvent" class="primaryBtn cursor-pointer">
      {{ isSelectedPack ? 'پرداخت' : 'انتخاب' }}
      <span class="check-mark-icon" :class="isSelectedPack ? 'selectedBg' : ''">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="10.3"
          height="10.596"
          viewBox="0 0 10.3 10.596"
        >
          <path
            id="Path_5478"
            data-name="Path 5478"
            d="M2909.139,3526.383c-.075-.01,2.781,3.814,2.781,3.814l4.552-7.632"
            transform="translate(-2907.887 -3520.85)"
            fill="none"
            :stroke="isSelectedPack ? '#53C786' : '#fff'"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2.5"
          />
        </svg>
      </span>
    </button>
  </div>
</template>
<script setup>
//emits
const emit = defineEmits(['selected'])

// props
const props = defineProps(['isSelectedPack'])

// functions
const emitClickEvent = function () {
  emit('selected')
}
</script>
<style scoped>
.check-mark-icon {
  padding: 3px;
  top: 8px;
  right: 8px;
  display: block;
  position: absolute;
  background-color: rgba(35, 31, 32, 0.1);
  width: 24px;
  height: 24px;
  border-radius: 100%;
}
.selectedBg {
  background-color: #ffffff !important;
}
</style>

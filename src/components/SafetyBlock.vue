<script>
import { defineProps, defineEmits, defineExpose, defineComponent } from 'vue'
export default defineComponent({
  name: 'SafetyBlock',
  props: {
    title: {
      type: String,
      required: true
    },
    text: {
      type: String,
      required: true
    }
  },
  setup(props) {
    return {
      props
    }
  }
})


</script>

<template>
    <div class="safetyBlock">
        <h1 class="safetyBlockTitle">{{ props.title }}</h1>
        <div class="safetyBlockText" v-html="props.text"></div>
</div>
</template>

<style scoped>

.safetyBlock {
    background-color: #1D1B1B;
    border-radius: 1rem;
    padding: 2rem;
    margin: 2rem;
    font-family: DM Sans;
    font-weight: 400;
    font-size: 1.5rem;
    color: white;
}

.safetyBlockTitle {
    font-size: 2rem;
    font-weight: 700;
    margin-bottom: 1rem;
}



</style>
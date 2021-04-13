<template>
  <button :class="classs"></button>
</template>

<script>
import { computed } from 'vue';
export default {
  name: 'ZllButton',
  props: {
    type: {
      type: String,
      default: 'primary',
      validator (type) {
        if (!['warning', 'danger', 'success', 'info', 'primary'].includes(type)) {
          throw new Error('button的type属性只能是' + ['warning', 'danger', 'success', 'info', 'primary'].join('、'));
        }

        return true;
      }
    }
  },
  setup (props) {
    const classs = computed(() => [
      'zll-button',
      `zll-button-${props.type}`
      ]);


    return {
      classs
    };
  }
}
</script>

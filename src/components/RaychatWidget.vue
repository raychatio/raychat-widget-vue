<template>
  <div>
    <!-- Vue component logic goes here -->
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import type { PropType } from 'vue';

declare global {
  interface Window {
    RAYCHAT_TOKEN: string;
  }
}

export default defineComponent({
  props: {
    token: {
      type: String as PropType<string>,
      required: true,
    },
    type: {
      type: String as PropType<string>,
      default: 'normal',
    },
  },
  mounted() {
    window.RAYCHAT_TOKEN = this.token;

    if (this.type === 'normal') {
      const script = document.createElement('script');
      script.src = 'https://widget-react.raychat.io/install/widget.js';
      script.async = true;
      document.head.appendChild(script);
    }
  },
});
</script>
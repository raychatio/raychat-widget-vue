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
    SEO_FRIENDLY: boolean;
    FAST_LOAD: boolean;
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
      default: 'NORMAL',
    },
  },
  mounted() {
    // Validate token
    if (!this.token || this.token.trim() === "") {
      console.error('Token for raychat widget is not provided.');
      return undefined;
    }

    // Validate type
    const validTypes = ['NORMAL', 'SEO_FRIENDLY', 'FAST_LOAD'];
    if (this.type && !validTypes.includes(this.type.toUpperCase())) {
      console.warn(
        `Provided type for raychat widget: "${this.type}" is not valid. using type "NORMAL" instead.`
      );
    }

    // Set widget token
    window.RAYCHAT_TOKEN = this.token;

    // Set widget load type
    if (this.type.toUpperCase() === "SEO_FRIENDLY") {
      window.SEO_FRIENDLY = true;
    } else if (this.type.toUpperCase() === "FAST_LOAD") {
      window.FAST_LOAD = true;
    }

    // Set the script to the head
    const script = document.createElement('script');
    script.src = 'https://widget-react.raychat.io/install/widget.js';
    script.async = true;
    document.head.appendChild(script);
  },
});
</script>
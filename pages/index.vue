<template>
  <div class="container mx-auto p-4 font-mono">
    <!-- Title -->
    <h3 class="text-3xl text-center mt-8">Vue Country Dropdown</h3>
    <!-- Dropdown -->
    <dropdown :settings="settings" />
    <!-- Settings -->
    <settings :settings="settings" />
    <!-- Links -->
    <links />
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "IndexPage",
  data() {
    return {
      settings: {
        enabledFlags: true,
        enabledCountryCode: true,
        showNameInput: true,
      },
    };
  },
});
</script>

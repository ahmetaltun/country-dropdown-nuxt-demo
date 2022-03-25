<template>
  <div class="flex flex-col text-center mt-8">
    <!-- enabledFlags -->
    <label>
      <input
        type="checkbox"
        v-model="settings.enabledFlags"
      > :enabledFlags
    </label>
    <!-- enabledCountryCode -->
    <label>
      <input
        type="checkbox"
        v-model="settings.enabledCountryCode"
      > :enabledCountryCode
    </label>
    <!-- showNameInput -->
    <label>
      <input
        type="checkbox"
        v-model="settings.showNameInput"
      > :showNameInput
    </label>
  </div>
</template>

<script>
export default {
  name: "settings",
  props: {
    settings: {
      type: Object,
      default: () => {
        return {
          enabledFlags: true,
          enabledCountryCode: true,
          showNameInput: true,
        }
      },
    }
  }
}
</script>

<style>
</style>
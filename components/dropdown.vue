<template>
  <div class="mt-6">
    <!-- Dropdown -->
    <div class="w-full text-center p-4">
      <vue-country-dropdown
        @onSelect="onSelect"
        :preferredCountries="['TR', 'US', 'GB']"
        :disabledFetchingCountry="true"
        :defaultCountryByAreaCode="90"
        :immediateCallSelectEvent="true"
        :enabledFlags="settings.enabledFlags"
        :enabledCountryCode="settings.enabledCountryCode"
        :showNameInput="settings.showNameInput"
        :showNotSelectedOption="true"
        :notSelectedOptionText="'Not Selected'"
      >
      </vue-country-dropdown>
    </div>
    <!-- Output -->
    <div class="text-center mt-4">
      {{ `{ name: "${selectedData.name}", iso2: "${selectedData.iso2}", dialCode: "${selectedData.dialCode}" }` }}
    </div>
  </div>
</template>

<script lang="ts">
import VueCountryDropdown from "vue-country-dropdown";

export default {
  name: "withoutProps",
  components: {
    VueCountryDropdown,
  },
  props: {
    settings: {
      type: Object,
      default: () => {
        return {
          enabledFlags: true,
          enabledCountryCode: true,
          showNameInput: true,
        };
      },
    },
    selectedData: {
      type: Object,
      default: () => {
        return {
          name: "",
          iso2: "",
          dialCode: "",
        };
      },
    },
  },
  data() {
    return {};
  },
  methods: {
    onSelect(data: Object) {
      Object.assign(this.selectedData, data);
    },
  },
};
</script>

<style>
</style>
<script>
import { __ } from '~/locale';
import LoadingIcon from '~/vue_shared/components/loading_icon.vue';

export default {
  components: {
    LoadingIcon,
  },
  props: {
    isDisabled: {
      type: Boolean,
      required: false,
      default: false,
    },
    isLoading: {
      type: Boolean,
      required: false,
      default: false,
    },
    toggleText: {
      type: String,
      required: false,
      default: __('Select'),
    },
  },
};
</script>

<template>
  <button
    :disabled="isDisabled || isLoading"
    class="dropdown-menu-toggle dropdown-menu-full-width"
    type="button"
    data-toggle="dropdown"
    aria-expanded="false"
  >
    <loading-icon
      v-show="isLoading"
      :inline="true"
    />
    <span class="dropdown-toggle-text">
      {{ toggleText }}
    </span>
    <span
      v-show="!isLoading"
      class="dropdown-toggle-icon"
    >
      <i
        class="fa fa-chevron-down"
        aria-hidden="true"
        data-hidden="true"
      ></i>
    </span>
  </button>
</template>

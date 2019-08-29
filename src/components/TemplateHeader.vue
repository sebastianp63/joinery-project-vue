<template>
  <div
    class="uk-container uk-width-2-3 uk-align-center uk-background-secondary uk-margin-remove-bottom"
  >
    <div class="uk-child-width-expand@s" uk-grid>
      <h6 class="uk-heading-small">1#</h6>
      <div>
        <button
          class="uk-button uk-button-primary"
          @click="hidden=!hidden"
        >{{ hidden ? "Show" : "Hide"}}</button>
        <button class="uk-button uk-button-danger">Delete</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    templateNumber: {
      type: Number,
      reqired: true
    }
  },
  data() {
    return {
      hidden: false
    };
  },
  watch: {
    hidden: {
      handler(old, val) {
        this.$emit("onHide", this.hidden);
      },
      deep: true
    }
  }
};
</script>

<style lang="scss" scoped>
.uk-container {
  border: 2px solid black;
}
</style>
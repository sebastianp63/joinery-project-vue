<template>
  <div
    class="uk-container uk-width-2-3 uk-align-center uk-background-muted uk-padding-small uk-margin-small-bottom"
  >
    <div class="uk-child-width-expand@s" uk-grid>
      <h6 class="uk-heading-small">1#</h6>

      <form action class="uk-form-horizontal">
        <label class="uk-form-label clearfix" for="first-name-template">First name:</label>
        <div class="uk-form-controls">
          <input class="uk-input" id="first-name-template" type="text" placeholder />
        </div>
      </form>
      <form action class="uk-form-horizontal">
        <label class="uk-form-label clearfix" for="last-name-template">Last name:</label>
        <div class="uk-form-controls">
          <input class="uk-input" id="last-name-template" type="text" placeholder />
        </div>
      </form>

      <div>
        <button class="uk-button uk-button-primary uk-button-small">Hide</button>
        <button class="uk-button uk-button-secondary uk-button-small">Delete</button>
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
  }
};
</script>

<style lang="scss" scoped>
</style>
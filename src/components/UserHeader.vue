<template>
  <div
    class="uk-container uk-width-2-3 uk-align-center uk-background-muted uk-padding-small uk-background-primary"
  >
    <div class="uk-child-width-expand@s" uk-grid>
      <form action class="uk-form-horizontal">
        <label class="uk-form-label" for="first-name-template">First name:</label>
        <div class="uk-form-controls">
          <input
            @input="getFirstName"
            class="uk-input"
            id="first-name-template"
            type="text"
            placeholder
          />
        </div>
      </form>
      <form action class="uk-form-horizontal">
        <label class="uk-form-label" for="last-name-template">Last name:</label>
        <div class="uk-form-controls">
          <input
            @input="getLastName"
            class="uk-input"
            id="last-name-template"
            type="text"
            placeholder
          />
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "UserHeader",
  props: {
    firstName: String,
    lastName: String
  },
  methods: {
    getFirstName(e) {
      this.$emit("inputFirstName", e.target.value);
    },
    getLastName(e) {
      this.$emit("inputLastName", e.target.value);
    }
  }
};
</script>

<style lang="scss" scoped>
</style>
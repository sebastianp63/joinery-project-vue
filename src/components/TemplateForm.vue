<template>
  <div class="uk-card uk-card-default uk-card-body">
    <h3 class="uk-card-title">Temaplate details</h3>
    <form>
      <fieldset class="uk-fieldset">
        <div class="uk-margin">
          <label class="uk-form-label" for="form-width">Width:</label>
          <div class="uk-form-controls">
            <input class="uk-input" id="form-width" type="number" placeholder />
          </div>
        </div>

        <div class="uk-margin">
          <label class="uk-form-label" for="form-height">Height:</label>
          <div class="uk-form-controls">
            <input class="uk-input" id="form-height" type="number" placeholder />
          </div>
        </div>

        <div class="uk-margin uk-grid-small uk-child-width-auto uk-grid">
          <label class="uk-form-label" for="form-width">Unit:</label>

          <label>
            <input class="uk-radio" type="radio" name="radio-unit" checked /> cm
          </label>
          <label>
            <input class="uk-radio" type="radio" name="radio-unit" /> mm
          </label>
        </div>

        <div class="uk-margin">
          <label class="uk-form-label" for="form-amount">Enter number of templates:</label>
          <div class="uk-form-controls">
            <input class="uk-input" id="form-amount" type="number" placeholder />
          </div>
        </div>
      </fieldset>
    </form>
  </div>
</template>

<script>
export default {
  name: "TemplateForm"
};
</script>


<style lang="scss" scoped>
</style>
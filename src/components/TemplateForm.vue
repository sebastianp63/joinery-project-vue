<template>
  <div class="uk-card uk-card-default uk-card-body">
    <h3 class="uk-card-title">Temaplate details</h3>
    <form>
      <fieldset class="uk-fieldset">
        <div class="uk-margin">
          <label class="uk-form-label" for="form-width">Width:</label>
          <div class="uk-form-controls">
            <input class="uk-input" id="form-width" type="number" v-model="state.width" />
          </div>
        </div>

        <div class="uk-margin">
          <label class="uk-form-label" for="form-height">Height:</label>
          <div class="uk-form-controls">
            <input class="uk-input" id="form-height" type="number" v-model="state.height" />
          </div>
        </div>

        <div class="uk-margin uk-grid-small uk-child-width-auto uk-grid">
          <label class="uk-form-label" for="form-width">Unit:</label>

          <label>
            <input
              class="uk-radio"
              type="radio"
              name="radio-unit"
              :checked="state.units === 'cm'"
              @input="state.units='cm'"
            /> cm
          </label>
          <label>
            <input
              class="uk-radio"
              type="radio"
              name="radio-unit"
              :checked="state.units === 'mm'"
              @input="state.units='mm'"
            /> mm
          </label>
        </div>

        <div class="uk-margin uk-grid-small uk-child-width-auto uk-grid">
          <label>
            <input
              class="uk-checkbox"
              type="checkbox"
              :checked="state.glue.includes('t')"
              @input="setGlue('t')"
            /> Top
          </label>
          <label>
            <input
              class="uk-checkbox"
              type="checkbox"
              :checked="state.glue.includes('b')"
              @input="setGlue('b')"
            /> Bottom
          </label>
          <label>
            <input
              class="uk-checkbox"
              type="checkbox"
              :checked="state.glue.includes('l')"
              @input="setGlue('l')"
            /> Left
          </label>
          <label>
            <input
              class="uk-checkbox"
              type="checkbox"
              :checked="state.glue.includes('r')"
              @input="setGlue('r')"
            /> Right
          </label>
        </div>
      </fieldset>
      <!-- {{state}} -->
    </form>
  </div>
</template>

<script>
export default {
  name: "TemplateForm",
  watch: {
    state: {
      handler(old, val) {
        if (val.height < 0 || val.height === "") {
          val.height = 0;
        }

        if (val.width < 0 || val.width === "") {
          val.width = 0;
        }

        if (val.width > this.validateData.maxWidthForCm && val.units === "cm") {
          val.width = this.validateData.maxWidthForCm;
        }

        if (
          val.height > this.validateData.maxHeightForCm &&
          val.units === "cm"
        ) {
          val.height = this.validateData.maxHeightForCm;
        }

        if (val.width > this.validateData.maxWidthForMm && val.units === "mm") {
          val.width = this.validateData.maxWidthForMm;
        }

        if (
          val.height > this.validateData.maxHeightForMm &&
          val.units === "mm"
        ) {
          val.height = this.validateData.maxHeightForMm;
        }

        this.$emit("onUpdated", this.state);
      },
      deep: true
    }
  },
  data() {
    return {
      validateData: {
        maxWidthForCm: 500,
        maxHeightForCm: 300,
        maxWidthForMm: 5000,
        maxHeightForMm: 3000
      },
      state: {
        id: 0,
        width: 100,
        height: 100,
        units: "mm",
        glue: ""
      }
    };
  },
  methods: {
    setGlue(glue) {
      let v = new Set(this.state.glue);

      if (this.state.glue.includes(glue)) {
        v.delete(glue);
      } else {
        v.add(glue);
      }

      this.state.glue = Array.from(v.values()).join("");
    }
  }
};
</script>

<style lang="scss" scoped>
</style>
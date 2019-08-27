<template>
  <div>
    <template-header></template-header>
    <div
      class="uk-container uk-width-2-3 uk-align-center uk-background-muted uk-padding uk-margin-small-top"
    >
      <div class="uk-child-width-expand@s uk-text-center" uk-grid>
        <div class="uk-width-1-3@m">
          <template-form></template-form>
        </div>
        <template-preview></template-preview>
      </div>
      <!-- <div class="uk-container uk-width-1-3">
      </div>
      <div class="uk-container uk-width-2-3">
      </div>-->
    </div>
  </div>
</template>


<script>
import TemplateForm from "./TemplateForm.vue";
import TemplateHeader from "./TemplateHeader.vue";
import TemplatePreview from "./TemplatePreview.vue";

export default {
  name: "Template",
  props: {
    msg: String
  },
  components: {
    TemplateForm,
    TemplateHeader,
    TemplatePreview
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

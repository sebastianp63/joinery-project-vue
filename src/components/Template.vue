<template>
  <div class="home">
    <template-header></template-header>
    <div
      class="uk-container uk-width-2-3 uk-align-center uk-background-muted uk-padding uk-margin-small-top"
    >
      <div class="uk-child-width-expand@s uk-text-center" uk-grid>
        <div class="uk-width-1-3@m">
          <template-form
            @getChangeCheckedTop="veneerSide.top = !veneerSide.top"
            @getChangeCheckedBottom="veneerSide.bottom = !veneerSide.bottom"
          ></template-form>
        </div>
        <template-preview v-bind:topBorder="veneerSide.top" v-bind:bottomBorder="veneerSide.bottom"></template-preview>
      </div>
    </div>
  </div>
</template>

<script>
import TemplateForm from "@/components/TemplateForm.vue";
import TemplateHeader from "@/components/TemplateHeader.vue";
import TemplatePreview from "@/components/TemplatePreview.vue";

export default {
  name: "Template",
  data: function() {
    return {
      width: 0,
      height: 0,
      veneerSide: {
        top: false,
        bottom: false
      }
    };
  },
  components: {
    TemplateForm,
    TemplateHeader,
    TemplatePreview
  },
  methods: {
    showData: function(value) {
      this.width = value;
      cosnole.log(this.width);
    }
  }
};
</script>

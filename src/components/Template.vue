<template>
  <div class="template">
    <template-header @onHide="hideTemplate"></template-header>

    <div
      class="uk-container uk-width-2-3 uk-align-center uk-background-muted uk-padding uk-margin-remove-top"
    >
      <div class="uk-child-width-expand@s uk-text-center" uk-grid>
        <div class>
          <template-form @onUpdated="onTemplateUpdate" />
        </div>
        <template-preview v-bind:templateData="templateData"></template-preview>
      </div>
      {{isHidden}}
    </div>
  </div>
</template>

<script>
import TemplateForm from "@/components/TemplateForm.vue";
import TemplateHeader from "@/components/TemplateHeader.vue";
import TemplatePreview from "@/components/TemplatePreview.vue";
import UserHeader from "@/components/UserHeader.vue";

export default {
  name: "template",
  data: function() {
    return {
      isHidden: false,
      templateData: {
        width: 100,
        height: 100,
        veneer: {
          top: false,
          bottom: false,
          left: false,
          right: false
        },
        unit: "mm"
      }
    };
  },
  components: {
    TemplateForm,
    TemplateHeader,
    TemplatePreview,
    UserHeader
  },
  methods: {
    onTemplateUpdate(data) {
      this.templateData.width = data.width;
      this.templateData.height = data.height;
      this.templateData.unit = data.units;
      this.templateData.veneer.top = data.glue.includes("t");
      this.templateData.veneer.bottom = data.glue.includes("b");
      this.templateData.veneer.left = data.glue.includes("l");
      this.templateData.veneer.right = data.glue.includes("r");

      // Webpack proxy API

      // axios.post('url', order).then((data) => {
      //   alert('Saved')
      // })
    },
    showData: function(value) {
      this.width = value;
      console.log(this.width);
    },
    hideTemplate(data) {
      console.log(data.hidden);
      data.hidden ? (this.isHidden = true) : (this.isHidden = false);
    }
  }
};
</script>

<style lang="scss" scoped>
.uk-container {
  border: 2px solid black;
}
</style>

<template>
  <div class="template">
    <template-header></template-header>
    <div
      class="uk-container uk-width-2-3 uk-align-center uk-background-muted uk-padding uk-margin-remove-top"
    >
      <div class="uk-child-width-expand@s uk-text-center" uk-grid>
        <div class>
          <template-form @onUpdated="onTemplateUpdate" />
        </div>
        <template-preview
          v-bind:topBorder="veneerSide.top"
          v-bind:bottomBorder="veneerSide.bottom"
          :leftBorder="veneerSide.left"
          :rightBorder="veneerSide.right"
        ></template-preview>
      </div>
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
      width: 0,
      height: 0,
      veneerSide: {
        top: false,
        bottom: false,
        left: false,
        right: false
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
      console.log(data);

      // Webpack proxy API

      // axios.post('url', order).then((data) => {
      //   alert('Saved')
      // })
    },
    showData: function(value) {
      this.width = value;
      console.log(this.width);
    }
  }
};
</script>

<style lang="scss" scoped>
.uk-container {
  border: 2px solid black;
}
</style>

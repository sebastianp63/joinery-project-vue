<template>
  <div
    class="uk-container uk-width-2-3 uk-align-center uk-background-secondary uk-margin-remove-bottom"
  >
    <div class="uk-child-width-expand@s" uk-grid>
      <p class="hedaer-id">#{{ templateNumber }} Template</p>
      <div>
        <button
          class="uk-button uk-button-primary"
          @click="hidden=!hidden"
        >{{ hidden ? "Show" : "Hide"}}</button>
        <button @click="deleteTemplate" class="uk-button uk-button-danger">Delete</button>
      </div>
    </div>
  </div>
</template>

<script>
import { bus } from "../main";

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
  },
  methods: {
    deleteTemplate: function() {
      bus.$emit("deleteTemplate", this.templateNumber);
    }
  }
};
</script>

<style lang="scss" scoped>
.uk-button {
  width: 20%;
  margin-right: 10px;
}
.uk-container {
  border: 2px solid black;
}
.hedaer-id {
  color: white;
  font-weight: bold;
  font-size: 30px;
  line-height: 40px;
}
</style>
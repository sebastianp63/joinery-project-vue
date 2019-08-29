<template>
  <div class="home">
    <UserHeader />
    <component v-for="component in templateComponent" v-bind:is="component"></component>
    <button @click="addNewTemplate">Add new template</button>
  </div>
</template>

<script>
// @ is an alias to /src
import Template from "@/components/Template.vue";
import UserHeader from "@/components/UserHeader.vue";

export default {
  name: "home",
  components: {
    Template,
    UserHeader
  },
  data() {
    return {
      templateComponent: ["Template"]
    };
  },
  methods: {
    addNewTemplate: function() {
      this.templateComponent.push("Template");
    }
  }
};
</script>

<template>
  <div class="home">
    <UserHeader />
    <!-- <component
      v-for="component in templateComponents"
      v-bind:key="component.index"
      v-bind:is="component.temp"
    ></component>-->

    <div v-for="el in templateComponents" v-bind:key="el.id">
      <Template v-bind:id="el.index"></Template>
    </div>
    <button
      class="uk-button uk-button-default uk-width-2-3 uk-margin-small-top"
      @click="addNewTemplate"
    >Add new template</button>
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
      id: 1,
      templateComponents: [{ index: 1 }]
    };
  },
  methods: {
    addNewTemplate: function() {
      this.id += 1;
      console.log(this.id);
      let exist = this.templateComponents.filter(element => {
        return element.index == this.id;
      });
      console.log();
      if (!exist.length > 0) {
        this.templateComponents.push({
          index: this.id
        });
      } else {
        console.log("this themplate has beenalready exist");
      }
    }
  }
};
</script>

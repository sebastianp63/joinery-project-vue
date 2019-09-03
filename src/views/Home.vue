<template>
  <div class="home">
    <!-- <UserHeader
      @inputFirstName="firstName = $event"
      :firstName="firstName"
      @inputLastName="lastName = $event"
      :lastName="lastName"
    />-->
    <button
      class="uk-button uk-button-default uk-width-2-3 uk-margin-small-top"
      @click="addNewTemplate"
    >Add new template</button>
    <component
      v-for="(component,id) in templateComponents"
      v-bind:key="component.index"
      v-bind:is="component.temp"
      v-bind:id="id"
    ></component>

    <!-- <div
      v-for="(el, index) in templateComponents"
      v-bind:key="el.id "
      v-on:delete-row="deleteThisRow(index)"`
    >
      <Template v-bind:id="index"></Template>
    </div>-->
    <button
      class="uk-button uk-button-default uk-width-2-3 uk-margin-small-top"
      @click="addNewTemplate"
    >Add new template</button>
    <div>{{templateComponents}}</div>
  </div>
</template>

<script>
// @ is an alias to /src
import MyTemplate from "@/components/MyTemplate.vue";
import UserHeader from "@/components/UserHeader.vue";

import { bus } from "../main";

export default {
  name: "home",
  components: {
    MyTemplate,
    UserHeader
  },
  watch: {
    $route(to, from) {
      console.log(this.$route.params.id);
    }
  },
  data() {
    return {
      id: 1,
      templateComponents: [{ index: 1, temp: "MyTemplate" }],
      firstName: {
        type: String,
        default: ""
      },
      lastName: {
        type: String,
        default: ""
      }
    };
  },
  created() {
    bus.$on("deleteTemplate", data => {
      console.log("byussss");
      this.deleteThisRow(data);
    });
  },

  methods: {
    addNewTemplate: function() {
      this.id += 1;
      let exist = this.templateComponents.filter(element => {
        return element.index == this.id;
      });
      if (!exist.length > 0) {
        this.templateComponents.push({
          index: this.id,
          temp: "Template"
        });
      } else {
        console.log("this themplate has been already exist");
      }
    },

    deleteThisRow: function(index) {
      if (this.templateComponents.length > 1) {
        this.templateComponents.splice(index, 1);
      }
      // if (this.templateComponents.length > 1) {
      //   console.log("start index: " + index);
      //   const itemToRemove = index - 1;
      //   // console.log("index to remove: " + itemToRemove);
      //   this.templateComponents.splice(itemToRemove, 1);
      //   // this.templateComponents = this.templateComponents
      //   //   .slice(0, itemToRemove)
      //   //   .concat(this.templateComponents.slice(-itemToRemove));

      //   // console.log(this.templateComponents);
      //   this.id = index;
      //   // console.log("size: " + this.templateComponents.length);
      //   for (let i = itemToRemove; i < this.templateComponents.length; i++) {
      //     this.templateComponents[i].index = this.id;
      //     if (this.id < this.templateComponents.length - 1) this.id++;
      //   }

      //  }
    }
  }
};
</script>

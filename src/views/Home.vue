<template>
  <div class="home">
    <TemplateForm></TemplateForm>
  </div>
</template>

<script>
// @ is an alias to /src
import TemplateForm from "@/components/TemplateForm.vue";

export default {
  name: "home",
  components: {
    TemplateForm
  }
};
</script>

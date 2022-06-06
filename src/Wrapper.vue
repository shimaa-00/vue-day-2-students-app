<template>
  <headcomponentVue />
  <div class="container">
    <div class="row">
      <div class="col-4">
        <linkscomponent-vue />
      </div>
      <div class="col-8">
        <bodycomponentVue />
      </div>
    </div>
  </div>
  <footercomponentVue />
</template>
<script>
import headcomponentVue from "./components/headcomponent.vue";
import linkscomponentVue from "./components/linkscomponent.vue";
import bodycomponentVue from "./components/bodycomponent.vue";
import footercomponentVue from "./components/footercomponent.vue";
export default {
  components: {
    headcomponentVue,
    linkscomponentVue,
    bodycomponentVue,
    footercomponentVue,
  },
};
</script>

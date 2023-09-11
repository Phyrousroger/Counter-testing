<template>
  <div>

    <nav class="navbar navbar-expand-lg bg-light shadow-lg">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">My App</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
          <NavItem
              v-for="{link,index} in links " :key="index"/>


          </ul>

        </div>
      </div>
    </nav>
  </div>
</template>

<script>
import NavItem from "./NavItem.vue";
export default {
  components: {NavItem},
  data() {

    return {
      links: ['one','two','three','four'],
    }
  },

}
</script>

<style scoped>

</style>
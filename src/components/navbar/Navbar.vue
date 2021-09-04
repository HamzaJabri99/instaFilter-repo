<template>
  <nav class="navbar-outer flexbox flex">
    <navbar-brand title="InstaFilter" class="brand" />
    <navbar-item text="Home" class="nav-item"></navbar-item>
    <navbar-item text="About" class="nav-item"></navbar-item>
    <navbar-item text="Contact" class="nav-item"></navbar-item>
  </nav>
</template>

<script>
import Navbar_Brand from "./Navbar_Brand";
import Navbar_NavItem from "./Navbar_NavItem";
export default {
  components: {
    "navbar-brand": Navbar_Brand,
    "navbar-item": Navbar_NavItem,
  },
};
</script>

<style scoped>
.navbar-outer {
  min-height: 50px;
  background-color: #240046;
  font-weight: bold;
  width: 100%;
  display: flex;
  gap: 0px;
  overflow: hidden;
  font-size: 120%;
}
@media screen and (max-width: 600px) {
  .navbar-outer {
    display: flex;
    gap: 18px;
  }
  .brand {
    margin-left: 0.3rem;
    padding: 0;
    font-size: 0.8rem;
  }
  .nav-item {
    width: rem;
    font-size: 0.8rem;
    overflow: hidden;
    margin-left: 1rem;
    gap: 18px;
  }
}
</style>

<template>
  <header class="header">
    <nav class="navbar container">
      <div class="logo">
        <NuxtLink to="/">
          <Logo />
        </NuxtLink>
      </div>
      <div class="links">
        <HeaderLink href="/" isExtended>Product</HeaderLink>
        <HeaderLink href="/">Pricing</HeaderLink>
      </div>
      <div class="auth-buttons">
        <CustomButton href="/" :color="Color.TextGray">Sign In</CustomButton>
        <CustomButton href="/" :color="Color.White" :bgColor="Color.BaseOrange"
          >Sign Up</CustomButton
        >
      </div>
    </nav>
  </header>
</template>
<script>
import Color from "../../assets/colors";

import Logo from "../icons/Logo";
import HeaderLink from "./HeaderLink";
import CustomButton from "../CustomButton";

export default {
  data() {
    return {
      Color,
    };
  },
  components: {
    Logo,
    HeaderLink,
    CustomButton,
  },
};
</script>

<style lang="scss" scoped>
@import "../../scss/index.scss";
@import "../../scss/colors.scss";

.header {
  display: flex;
  padding: 10px 0;
  background-color: $white;

  .navbar {
    display: flex;
    align-items: center;
    padding: 15px;

    .logo {
      margin-left: 15px;

      svg {
        fill: $base-orange;
      }
    }

    .links {
      display: flex;
      margin-left: 50px;
    }
  }

  .auth-buttons {
    margin-left: auto;
  }
}
</style>

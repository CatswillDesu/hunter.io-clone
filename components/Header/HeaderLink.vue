<template>
  <NuxtLink class="link" :class="{ extended: isExtended }" :to="href"
    ><slot></slot
  ></NuxtLink>
</template>
<script>
export default {
  props: {
    href: String,
    isExtended: Boolean,
  },
};
</script>

<style lang="scss" scoped>
@import "../../scss/colors.scss";
.link {
  position: relative;
  font-size: 15px;
  text-decoration: none;
  color: $text-gray;
  margin-right: 35px;

  &:last-child {
    margin-left: 0;
  }
}

.extended {
  margin-right: 45px;

  &::after {
    content: "";
    position: absolute;
    right: -15px;
    top: 7px;
    display: inline-block;
    width: 9px;
    height: 9px;
    background-image: url("../../assets/right-arrow.svg");
    transform: rotate(90deg);
  }
}
</style>

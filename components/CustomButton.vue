<template>
  <NuxtLink v-if="href" :to="href" class="custom-button" :style="stylesObj"
    ><slot></slot
  ></NuxtLink>
  <button v-else class="custom-button" :style="stylesObj"><slot></slot></button>
</template>
<script>
export default {
  data() {
    return {
      stylesObj: {
        color: this.color,
        backgroundColor: this.bgColor ? this.bgColor : "transparent",
        fontSize: this.fontSize ? this.fontSize + "px" : "15px",
        fontWeight: this.isBold ? "700" : "400",
      },
    };
  },
  props: {
    color: String,
    bgColor: String,
    fontSize: Number,
    isBold: Boolean,
    href: String,
  },
  created() {
    console.log(this.fontSize);
  },
};
</script>
<style lang="scss" scoped>
.custom-button {
  padding: 7px 18px;
  border: none;
  border-radius: 3px;
  margin-right: 20px;
  text-decoration: none;

  &:last-child {
    margin-right: 0;
  }
}
</style>

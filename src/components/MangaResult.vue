<template>
    <p>
        <img src="@/assets/01.gif">
        <img v-if="koma1" :src="image_path(koma1)">
        <img v-if="koma2" :src="image_path(koma2)">
        <img v-if="koma3" :src="image_path(koma3)">
    </p>
</template>

<script>
export default {
  props: {
      koma1: String,
      koma2: String,
      koma3: String
  },
  computed: {

  },
  methods:{
    image_path: function(filename){
      return require("@/assets/" + filename);
    }
  }
}
</script>
<style scoped>
p{
    text-align: center;
}
</style>
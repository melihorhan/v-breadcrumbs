<template>
  <ul class="breadcrumb">
    <li v-for="item in items" :key="item.href">
      <a v-show="item.href && item.href.length>0 && !item.actvie" :href="item.href">{{item.text}}</a>
      <span v-show="item.active && item.active === true">{{item.text}}</span>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    items: {
      type: Array,
      required: true,
      default: () => []
    }
  }
};
</script>

<style scoped>
ul.breadcrumb {
  padding: 10px 16px;
  list-style: none;
  background-color: #eee;
}

ul.breadcrumb li {
  display: inline;
  font-size: 18px;
}

ul.breadcrumb li + li:before {
  padding: 8px;
  color: black;
  content: "/\00a0";
}

ul.breadcrumb li a {
  color: #0275d8;
  text-decoration: none;
}

ul.breadcrumb li a:hover {
  color: #01447e;
  text-decoration: underline;
}
</style>

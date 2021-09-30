<template>
    <div class="books">
      <p class="books__title">{{products_data.title}}</p>
      <ul class="books__menu">
        <li class="menu-item">
          <div class="menu-item">
            <p>
              {{products_data.content}}
              (<span> {{gotQuantity}} </span>)
            </p>
            <span class="item-span">{{ gotPrice }} </span>
          </div>
        </li>
      </ul>
    </div>
</template>

<script>
import { defineComponent } from "vue";
export default defineComponent({
  name: "PageIndex",
  props: {
    products_data: {
      type: Object,
      default() {
        return {};
      },
    },
  },
  computed: {
    gotPrice() {
      return this.products_data.C;
    },
    gotQuantity() {
      return this.products_data.P;
    },
  },
  mounted() {
    // this.products_data.map(item => console.log(item))
    console.log(this.products_data, "data");
  },
});
</script>

<style lang="scss" scoped>
h1 {
  margin: 0;
}
.books {
  display: flex;
  background: rgb(159, 181, 255);
  flex-direction: column;
  /* max-width: 700px; */
  width: 100%;
  border-radius: 5px;
}
.books__title {
  font-size: 24px;
  text-align: start;
  margin: 0;
}

.books__menu {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  border: none;
  border-radius: 5px;
  list-style: none;
  margin: 0;
  padding: 0;
  width: 100%;
}

.menu-item {
  font-size: 14px;
  border: 0.5px solid black;
  background: #fff;
  width: 100%;
  display: flex;
  border-radius: 4px;
  text-align: center;
  justify-content: space-between;
}
.menu-item > p {
  padding: 1px;
  margin: 0;
}
.item-span {
  background: rgba(85, 167, 255, 0.727);
  color: #000;
  padding: 10px;
  width: 40px;
  align-items: center;
}
</style>

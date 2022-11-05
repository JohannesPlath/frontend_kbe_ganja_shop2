<template>
  <ul>
    <MainProductListItem
        v-for="dope in dopes" :key="dope.id"
        :item="dope"
        :class="{'isAdded':dope.isAddedAtCard}"
        @toggle="toggleListItem"
        />
  </ul>

</template>

<script>
import MainProductListItem from "@/components/MainProductListItem";
export default {
  name: "main_products.vue",
  data: () => ({
  dopes: [
    {id: 1, name: "White Widow", isAddedToCard: false },
    {id: 2, name: "Purple Hase", isAddedToCard: false},
    {id: 3, name: "orange Butt", isAddedToCard: false},
    {id: 4, name: "...Skunk...", isAddedToCard: false},
  ],
  }),
  components:{
    MainProductListItem,
  },
  methods:{
    toggleListItem(elem){
      elem.isAddedAtCard = !elem.isAddedAtCard;
    }
  },
}
</script>

<style scoped>
.isAdded{
  text-decoration: line-through;
}
</style>
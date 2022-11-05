<template>
  <li  :class="{'isAddedToCard':item.isAddedToCard}">

    {{item.name}}
    <button v-on:click="addItemToCard">buy</button>
    <button @click="getDedailedInformation">get detail</button>
    <button @click="removeFromCard">remove from bucked</button>
  </li>

</template>

<script>
export default {
  name: "MainProductListItem",
  props: ['item'],
  methods: {
    addItemToCard(){
      //todo
      this.toggleItem();
      alert("weed is added");
    },
    getDedailedInformation(){
      alert(" a lot of sensless informations that nobody likes to read...");
    },
    removeFromCard(){
      //todo
      this.toggleItem();
      alert("weed is removed");
    },
    toggleItem(){
      this.$emit('toggle', this.item);
    },

  }
}
</script>

<style scoped>
.itemDesign{
  display: flex;
  justify-content: center;
  flex-direction: column;
  width: fit-content;
}
</style>
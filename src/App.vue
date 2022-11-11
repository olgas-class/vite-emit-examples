<script>
import FancyButton from './components/FancyButton.vue';
import ShoppingItem from './components/ShoppingItem.vue';
import NewItemInput from './components/NewItemInput.vue';
import { store } from "./store";

export default {
  components: {
    FancyButton,
    ShoppingItem,
    NewItemInput
  },
  data() {
    return {
      store,
      firstClickNumber: 0
    }
  },
  methods: {
    incrementFirst() {
      this.firstClickNumber++;
    },
    showAlert() {
      alert("Ciaoooo")
    },
    //         "pane"
    addNewItem(data) {
      console.log("Aggiungi!", data);
      this.store.shoppingList.push(data)
    }
  }
}
</script>

<template>
  <!-- Esempio componente bottone -->
  <section class="container">
    <h1>Ciao</h1>
    <FancyButton @btnClicked="incrementFirst" buttonText="ciao, sono bottone" />
    <span>Il bottone è stato cliccato {{ firstClickNumber }} volte</span>
    <FancyButton @btnClicked="showAlert" buttonText="secondo bottone" />
  </section>

  <!-- Esempio componente shopping list -->
  <section class="container mt-4">
    <h2>My shopping list</h2>
    <NewItemInput @addBtnClicked="addNewItem" />
    <div>
      <ShoppingItem v-for="(item, index) in store.shoppingList" :key="index" :toBuyItem="item" />
    </div>
  </section>

</template>
<script>
export default {
    name: "NewItemInput",
    data() {
        return {
            newItemText: ""
        }
    }
}
</script>

<template>
    <div class="form-group">
        <label for="new-item">Aggiungi un nuovo item</label>
        <input type="text" id="new-item" class="form-control" v-model="newItemText">
        <!--                                       "pane" -->
        <button @click="$emit('addBtnClicked', newItemText)" class="btn btn-primary">Aggiungi</button>
    </div>

</template>
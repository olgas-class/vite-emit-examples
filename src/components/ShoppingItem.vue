<script>
export default {
    name: "ShoppingItem",
    props: {
        toBuyItem: String
    }
}
</script>

<template>
    <div class="d-flex">
        <p>{{ toBuyItem }}</p>
    </div>
</template>
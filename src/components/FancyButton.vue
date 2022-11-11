<script>
export default {
    name: "FancyButton",
    props: {
        buttonText: String
    }
}
</script>

<template>
    <button @click="$emit('btnClicked')" class="btn btn-fancy">{{ buttonText }}</button>
</template>

<style scoped>
.btn-fancy {
    background-image: linear-gradient(to bottom right, violet, blue);
    color: white;
}
</style>
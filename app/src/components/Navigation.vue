<template>
    <div class="content">
        <div v-for="color of colors" :key="color">
            <div class="input-group">
                <label for="100">{{color.name}}</label>
                <input class="input" type="text" :name="color.name" v-model="color.value" :placeholder="color.value" />
            </div>
        </div>
    </div>
</template>

<script lang="ts">
export default {
    props: {
        colors: Object
    },
}
</script>

<style lang="postcss" scoped>
.input-group {
    @apply mb-2;
}

label {
    @apply mb-5;
}
</style>
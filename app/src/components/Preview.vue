<template>
    <div class="h-full flex justify-center items-center">
        <div v-for="color of colors" v-bind:key="color">
            <div class="box text-gray-900" v-bind:style="{backgroundColor: color.value}">
                <p>{{color.name}}</p>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
export default {
    props: {
        colors: Array
    },
}
</script>

<style lang="postcss" scoped>
    .box {
        @apply p-7 rounded-lg mr-6;
    }

    p {
        @apply text-xl font-medium;
    }
</style>
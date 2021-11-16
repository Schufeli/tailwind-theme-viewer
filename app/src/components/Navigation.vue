<template>
    <div class="content">
        <div v-for="color of colors" :key="color">
            <div class="input-group">
                <label for="100">{{color.name}}</label>
                <div class="relative">
                    <input class="input" type="text" :name="color.name" v-model="color.value" :placeholder="color.value" />
                    <span v-bind:style="{backgroundColor: color.value}"></span>
                </div>
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
    @apply mb-2 mx-7;
}

span {
    right: 0;
    @apply w-11 h-full absolute z-10 rounded-r border-t-2 border-r-2 border-b-2 opacity-95;
}

label {
    @apply mb-5;
}
</style>
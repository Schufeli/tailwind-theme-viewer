<template>
    <div class="fixed z-20 inset-0 overflow-y-auto" aria-labelledby="modal-title" role="dialog" aria-modal="true">
        <div class="flex items-end justify-center min-h-screen pt-4 px-4 pb-20 text-center sm:block sm:p-0">
            <div @click="close()" class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity" aria-hidden="true"></div>

            <span class="hidden sm:inline-block sm:align-middle sm:h-screen" aria-hidden="true">&#8203;</span>
            <div class="inline-block align-bottom bg-white rounded-lg text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle">
            <div class="bg-white px-4 pt-5 pb-4 sm:p-6 sm:pb-4 max-w-5xl">
                <div class="sm:flex sm:items-start">
                    <div class="mx-auto flex-shrink-0 flex items-center justify-center h-12 w-12 rounded-full bg-blue-100 sm:mx-0 sm:h-10">
                        <span class="material-icons text-blue-600">file_download</span>
                    </div>
                    <div class="mt-3 text-center sm:mt-0 sm:ml-4 sm:text-left">
                        <h3 class="text-lg leading-6 font-medium text-gray-900" id="modal-title">
                        Export Theme
                        </h3>
                        <!-- Content before entered -->
                        <div class="mt-2">
                            <p class="text-sm text-gray-500 mb-5">Here is your exported theme. You can copy paste it to your tailwind.config.js file.</p>
                        </div>
                    </div>
                </div>
                <pre><code>{{ output }}</code></pre>
            </div>
            <div class="bg-gray-50 px-4 py-3 sm:px-6 sm:flex sm:flex-row-reverse">
                <button @click="close()" type="button" class="mt-3 w-full inline-flex justify-center rounded-md border border-gray-300 shadow-sm px-4 py-2 bg-white text-base font-medium text-gray-700 hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500 sm:mt-0 sm:ml-3 sm:w-auto sm:text-sm">
                Close
                </button>
            </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
export default {
    props: {
        colors: Array
    },
    data() {
        return {
            name: 'Custom',
            valid: true,
            nameEntered: false,
            output: this.stringify()
        }
    },
    methods: {
        close(): void {
            this.$emit('toggle');
            this.nameEntered = false;
        },
        stringify() {
            return `extend: { 
    colors: {
        custom: {
            100: "${this.colors[0].value}"
            200: "${this.colors[1].value}"
            300: "${this.colors[2].value}"
            400: "${this.colors[3].value}"
            500: "${this.colors[4].value}"
            600: "${this.colors[5].value}"
            700: "${this.colors[6].value}"
            800: "${this.colors[7].value}"
            900: "${this.colors[8].value}"
        }
    }
}`
        }  
    }
}
</script>

<style lang="postcss" scoped>
    pre {
        @apply bg-gray-300 rounded-lg p-5;
    }
</style>
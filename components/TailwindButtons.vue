<script>
export default {
  props: ['buttonType'],
}
</script>

<template>
    <div>
        <button v-if="buttonType == 'icon'" class="px-6 py-2.5 text-black rounded-lg bg-green-300 hover:bg-green-400 inline-flex items-center mt-2" type="button">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 mr-2">
                <path stroke-linecap="round" stroke-linejoin="round" d="M6 12L3.269 3.126A59.768 59.768 0 0121.485 12 59.77 59.77 0 013.27 20.876L5.999 12zm0 0h7.5" />
            </svg>
            Send email
        </button>
        <button v-if="buttonType == 'standard'" class="px-6 py-2.5 text-white bg-blue-500 rounded-lg hover:bg-blue-600 mt-2" type="button">
            Standard
        </button>
        <button v-if="buttonType == 'outlined'"
            class="px-6 py-2.5 text-blue-500 border-2 border-blue-500 bg-white rounded-lg hover:bg-blue-500 hover:text-white mt-2" 
            type="button">
            Outlined
        </button>
        <button v-if="buttonType == 'square'" class="px-6 py-2.5 text-white bg-gray-900 hover:bg-black mt-2" type="button">
            Dark & Square
        </button>
        <button v-if="buttonType == 'rounded'" class="px-6 py-2.5 text-white rounded-full bg-pink-500 hover:bg-pink-600 mt-2" type="button">
            Fully Rounded
        </button>
        <div v-if="buttonType == 'raised'" class="p-8 bg-gray-50">
            <button 
                class="px-8 py-3 shadow-2xl text-yellow-500 rounded bg-white hover:bg-gray-50 mt-2" 
                type="button">
                Raised
            </button>
        </div>
        <button v-if="buttonType == 'smooth'" class="px-8 py-3 text-red-500 rounded bg-red-100 mt-2" type="button">
            Smooth
        </button>
    </div>
</template>

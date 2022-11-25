<template>
    <img class="border-4 border-black p-2" :src="this.imageUrl" />
</template>

<script>
export default {
  name: 'ContentImage',
  props: ['imageUrl']
}
</script>
<template>

    <button class="button">{{ text }}</button>
    
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent ({
    props: {
        text: String,
    },
});
</script>

<style>

    .button {
        color: red;
    }

</style>
<script setup lang="ts">

const props = defineProps<{
    cardHeader: string;
    cardSubheader: string;
    cardContent: string;
}>();

</script>

<template>
    <article>
        <h2>{{ cardHeader }}</h2>
        <sper class="subheading">{{ cardSubheader }}</sper>
        <p class="">{{ cardContent }}</p>
    </article>
</template>

<style lang="scss" scoped>
article {
    background-color: $white-color;
    color: $forest-color;
    border-radius: $small-card-border-radius;
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    padding: 1.25rem;
    filter: drop-shadow(rgba(0, 0, 0, 0.25) -4px 4px 4px);
    h2 {
        font-family: $primary-font;
        font-size: $h3-fontsize;
        text-transform: uppercase;
        margin: 0;
    }
    .subheading {
        font-family: $secondary-font;
        font-size: $subhead-fontsize;
        margin: 0;
    }
    p {
        font-family: $secondary-font;
        font-size: $body-fontsize;
        margin: 0;
    }
}
</style>
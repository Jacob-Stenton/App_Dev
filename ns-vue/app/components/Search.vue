<template>
    <Page>
        <ActionBar>
            <Label text="Search"></Label>
        </ActionBar>
        <StackLayout orientation="vertical">
            <SearchBar hint="Search..." v-model="searchQuery" />
            <items :items = "items"/>
        </StackLayout>
    </Page>
</template>

<script>
import { StackLayout } from "@nativescript/core";
import { ref } from "@vue/composition-api";

export default {
    setup(){
        const message = ref("<!-- Search page content goes here -->");

        return {
            message
        };
    }
};
</script>

<style lang="scss" scoped>
    // Start custom common variables
    @import "@nativescript/theme/scss/variables/blue";
    // End custom common variables

    // Custom styles

</style>

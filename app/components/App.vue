<template lang="html">
<Page>
    <Label Text="Lesson shop" class="h2"/>


    <BottomNavigation selectedIndex="0">
        <TabStrip class="bottom_navigation">
            <TabStripItem class="navigation__item">
                <Label text="Checkout"></Label>
            </TabStripItem>
            <TabStripItem class="navigation__item">
                <Label text="LessonList"></Label>
            </TabStripItem>
        </TabStrip>

        <TabContentItem>
            <Frame id="Checkout">
                <Checkout />
            </Frame>
        </TabContentItem>

        <TabContentItem>
            <Frame id="LessonList">
                <LessonList />
            </Frame>
        </TabContentItem>

    </BottomNavigation>
    </Page>
</template>

<script>
    import Checkout from "./Checkout.vue";
    import LessonList from "./LessonList.vue";

    export default {
        components: {
            Checkout,
            LessonList
        }
    };
</script>

<style>
</style>
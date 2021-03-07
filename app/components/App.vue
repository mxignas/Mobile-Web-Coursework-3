<template lang="html">
    <BottomNavigation selectedIndex="0">
        <TabStrip class="bottom_navigation">
            <TabStripItem class="navigation__item">
                <Label text="Checkout"></Label>
                <Image src.decode="font://&#xf03d;" class="fas t-36"></Image>
            </TabStripItem>
            <TabStripItem class="navigation__item">
                <Label text="LessonList"></Label>
                <Image src.decode="font://&#xf124;" class="fas t-36"></Image>
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
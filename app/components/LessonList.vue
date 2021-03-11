<template>
    <Page>
        <ActionBar title="LessonList!"/>
    <ListView for="product in products" @itemTap="onItemTap" >
        <!-- displaying items with v-template -->
        <v-template >
            <StackLayout>
                <Label :text="`Lesson: ${product.Activity}`" class="ProductInfo"/>
                <Label :text="`Location: ${product.Location}`" class="ProductInfo"/>
                <Label :text="`Price: ${product.Price}`" class="ProductInfo"/>
                <Label :text="`Availability: ${product.Availability}`" class="ProductInfo"/>
                <Image :src="`${product.url}`" ></Image>
            </StackLayout>
        </v-template>
    </ListView>
</Page>
</template>

<script>
export default {
    data() {

	    return {
            // my products
            products: [
                { id: 1001, url: "~/assets/Math.png", Title: "Lessons", Activity: "Math", Location: "West End", Price: 100, Availability: 5 },
                { id: 1002, url: "~/assets/Soccer.png", Title: "Sports", Activity: "Soccer", Location: "Hendon", Price: 50, Availability: 5 },
                { id: 1003, url: "~/assets/English.png", Title: "Lessons", Activity: "English", Location: "Kensington", Price: 80, Availability: 5 },
                { id: 1004, url: "~/assets/Boxing.png", Title: "Sports", Activity: "Boxing", Location: "Hendon", Price: 60, Availability: 5 },
                { id: 1005, url: "~/assets/Art.png", Title: "Lessons", Activity: "Art", Location: "London", Price: 80, Availability: 5 },
                { id: 1006, url: "~/assets/Tennis.png", Title: "Sports", Activity: "Tennis", Location: "Westminster", Price: 150, Availability: 5 },
                { id: 1007, url: "~/assets/Science.png", Title: "Lessons", Activity: "Science", Location: "London", Price: 120, Availability: 5 },
                { id: 1008, url: "~/assets/Volleyball.png", Title: "Sports", Activity: "Volleyball", Location: "Camden Town", Price: 50, Availability: 5 },
                { id: 1009, url: "~/assets/Geography.png", Title: "Lessons", Activity: "Geography", Location: "London", Price: 60, Availability: 5 },
                { id: 1010, url: "~/assets/Basketball.png", Title: "Sports", Activity: "Basketball", Location: "Soho", Price: 95, Availability: 5 },
                ],
        };
    },
    methods: {
        onItemTap(event) {
            // passing event.item through addProduct
            this.$emit('AddProduct', event.item)
        }
    },
};
</script>

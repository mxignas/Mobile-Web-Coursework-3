<template>
    <Page>
        <StackLayout>
            <Label class="h2 text-center" text="Shopping Cart" />
            <Label class="h2 text-center" text="(Tap a product to remove it)" />
                <ListView for="product in cart" @itemTap='onItemTap'>
                    <v-template>
                        <StackLayout>
                            <Label :text="product.Activity" />
                            <Label :text="`Price: ${product.Price}`" />
                            <Label :text="`Inventory: ${product.Availability}`" />
                        </StackLayout>
                    </v-template>
                </ListView>

            <TextField hint='Name' v-model='name'/>
            <TextField hint='Phone number' v-model='phoneNr'/>
            <Button @tap='submitOrder' text='Submit Order'/>
        </StackLayout>
    </Page>
</template>


<script>
export default {
    props: ['cart'],
    methods: {
        onItemTap(event) {
        this.$emit("removeProduct", event.item);
        },
        submitOrder() {
            alert('An order is placed by ' + this.name + " at " + this.phoneNr)
}
    },
    data() {
	    return {
	    };
    }
}
</script>

<style>
</style>
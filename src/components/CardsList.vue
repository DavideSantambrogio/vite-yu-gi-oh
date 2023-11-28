<script>
import{store} from "../store";
import CardCard from "./CardCard.vue";
export default {
    data() {
        return {
            store
        };
    },
    components: { CardCard }
}
</script>

<template>
    <section class="container mt-5">
        <h2>Lista di carte</h2>
        <div class="row row-cols-5 g-4">
            <div class="col" v-for="card in store.cardsList">
                <CardCard :card="card"/>

            </div>
        </div>
    </section>

</template>

<style lang="scss" scoped>
section {
    background-color: white;
}

</style>
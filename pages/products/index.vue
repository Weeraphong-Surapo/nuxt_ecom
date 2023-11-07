<template>
    <div>
        <h1>Products All</h1>
        <div v-if="loding"  class="d-flex justify-content-center align-items-center">
            <div class="spinner-grow text-primary " style="width: 3rem; height: 3rem;" role="status">
                <span class="visually-hidden">Loading...</span>
            </div>
        </div>
        <div v-else>
            <div class="row">
                <div v-for="i in 10" :key="i" class="col-12 col-md-6 col-lg-4 col-xl-3 p-2 gx-0 gy-3">
                    <ProductCard :product="i" />
                </div>
            </div>
        </div>

    </div>
</template>

<script>
export default {
    data() {
        return {
            loding: true
        }
    },
    mounted() {
        setTimeout(() => {
            this.loding = false
        }, 500);
    }
}
</script>

<style scoped></style>
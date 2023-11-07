<template>
    <div class="bg-white pb-3">
        <NuxtLink :to="{ name: 'products-id', params: { id: product } }">
            <div class="collection-img position-relative overflow-hidden">
                <img class="w-100"
                    src="https://imageio.forbes.com/specials-images/imageserve/64e74ad803781abed13b0612/Apple--iPhone--iPhone-15--iPhone-15-Pro--iPhone-15-Pro-Max--iPhone-15-release--new/0x0.jpg?format=jpg&crop=1275,956,x113,y0,safe&width=960"
                    alt="">
                <span
                    class="position-absolute bg-primary d-flex justify-content-center align-items-center text-white">sale</span>
            </div>
            <div class="text-center">
                <div class="rating mt-3">
                    <i class="fas fa-star text-primary"></i>
                    <i class="fas fa-star text-primary"></i>
                    <i class="fas fa-star text-primary"></i>
                    <i class="fas fa-star text-primary"></i>
                    <i class="fas fa-star text-primary"></i>
                </div>
                <p class="text-capitalize my-1">Iphone 12</p>
                <span class="fw-bold">24,000 บาท</span>
            </div>
        </NuxtLink>
    </div>
</template>

<script>
export default {
    props: ['product'],
    data() {
        return {

        }
    }
}
</script>

<style scoped>
.collection-img span {
    top: 20px;
    right: 20px;
    width: 46px;
    height: 46px;
    border-radius: 50%;
}

.collection-img img {
    transition: all 0.3s ease;
}

.collection-img:hover img {
    transform: scale(1.1);
}
</style>
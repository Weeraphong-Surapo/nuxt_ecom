<template>
    <section id="collection" class="py-5">
        <div class="container">
            <div class="title text-center">
                <h2 class="position-relative d-inline-block">สินค้าทั้งหมด</h2>
            </div>

            <div class="row g-0">
                <div class="d-flex flex-wrap justify-content-center mt-5">
                    <button type="button" class="btn text-dark m-2">ทั้งหมด</button>
                    <button type="button" class="btn text-dark m-2">เครื่องใช้ไฟฟ้า</button>
                    <button type="button" class="btn text-dark m-2">มือถือ</button>
                    <button type="button" class="btn text-dark m-2">หนังสือ</button>
                </div>
            </div>

            <div class="collection-list mt-4 row">
                <div class="col-12 col-md-6 col-lg-4 col-xl-3 p-2 gx-0 gy-3">
                    <div class="collection-img position-relative overflow-hidden">
                        <img class="w-100"
                            src="https://imageio.forbes.com/specials-images/imageserve/64e74ad803781abed13b0612/Apple--iPhone--iPhone-15--iPhone-15-Pro--iPhone-15-Pro-Max--iPhone-15-release--new/0x0.jpg?format=jpg&crop=1275,956,x113,y0,safe&width=960" alt="">
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
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {

}
</script>

<style scoped>
.title h2::before {
    position: absolute;
    content: "";
    width: 4px;
    height: 50px;
    background-color: var(--pink);
    left: -20px;
    top: 50%;
    transform: translateY(-50%);
}

.collection-img span {
    top: 20px;
    right: 20px;
    width: 46px;
    height: 46px;
    border-radius: 50%;
}
.collection-img img{
    transition: all 0.3s ease;
}

.collection-img:hover img{
    transform: scale(1.2);
}
</style>
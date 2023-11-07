<template>
    <div class="row">
        <div class="col-12">

            <div v-if="loding" class="d-flex justify-content-center align-items-center">
                <div class="spinner-grow text-primary " style="width: 3rem; height: 3rem;" role="status">
                    <span class="visually-hidden">Loading...</span>
                </div>
            </div>
            <div class="row" v-else>
                <BreadCrumb />
                <div class="col-lg-8 col-md-12 col-12">
                    <div class="p-3 mb-3 bg-white grid-product" >
                        <div class="img-product">
                            <img src="https://s.isanook.com/hi/0/ui/317/1588375/Apple-iPhone-15-Pro-lineup-hero-230912_Full-Bleed-Image-jpg-large.jpg"
                                class="img-product-item" alt="">
                        </div>
                        <div class="title-product">
                            <p class="text-wrap">กระจกทรงห้าเหลี่ยม ขาสั้น ใส่รูกระจกรถทั่วไปได้ งาน CNC (1คู่)</p>
                        </div>
                        <div class="price-product">
                            <p class="text-primary">฿34,000.00</p>
                            <div class="option-item">
                                <i class="fa-regular fa-heart icon text-muted"></i>
                                <i class="fa-regular fa-trash-can icon text-muted"></i>
                            </div>
                        </div>
                        <div class="quantity-product d-flex justify-content-center align-items-start">
                            <button class="btn-quantity">-</button>
                            <input class="input-qty-product" type="text" value="1">
                            <button class="btn-quantity">+</button>
                        </div>
                    </div>
                </div>

                <div class="col-md-12 col-lg-4 col-12">
                    <div class="position-sticky" style="top: 6.5rem;">
                        <div class="p-4 mb-3 bg-white">
                            <div class="">
                                <h4 class="text-title-cart text-dark">สรุปรายการสั่งซื้อ</h4>
                            </div>
                            <div class="d-flex justify-content-between mt-3">
                                <span class="text-muted text-title-row-cart">ยอดรวม (จำนวน 2 ชิ้น)</span>
                                <span class="text-dark fs-6">฿23,000.00</span>
                            </div>
                            <div class="d-flex justify-content-between my-3">
                                <span class="text-muted text-title-row-cart">ค่าจัดส่ง</span>
                                <span class="text-dark fs-6">฿100.00</span>
                            </div>
                            <div class="d-flex justify-content-between">
                                <span class="text-muted text-title-row-cart">ยอดรวมทั้งสิ้น </span>
                                <span class="text-dark fs-6">฿23,100.00</span>
                            </div>
                            <div class="d-flex justify-content-end  mb-4">
                                <span class="text-dark text-vat mt-1">รวมภาษีมูลค่าเพิ่ม (ถ้ามี)</span>
                            </div>
                            <router-link to="checkout" class="btn w-100">ดำเนินการชำระเงิน</router-link>
                        </div>
                    </div>

                </div>
            </div>
            <!-- <div class="card">
                <div class="card-body">
                    <div class="row">
                        <div class="col-md-8">
                            <div class="card" v-for="i in 20" :key="i">
                                <img class="card-img-top" src="holder.js/100x180/" alt="">
                                <div class="card-body">
                                    <h4 class="card-title">Title</h4>
                                    <p class="card-text">Text</p>
                                </div>
                            </div>

                        </div>

                        <div class="col-md-4">
                            <div class="position-sticky" style="top: 2rem;">
                                <div class="p-4 mb-3 bg-light rounded">
                                    <div class="">
                                        <h4>สรุปรายการสั่งซื้อ</h4>
                                    </div>
                                    <div class="d-flex justify-content-between">
                                        <span class="text-muted">ยอดรวม (จำนวน 2 ชิ้น)</span>
                                        <span class="text-dark fs-6">฿23,000.00</span>
                                    </div>
                                    <div class="d-flex justify-content-between my-4">
                                        <span class="text-muted">ค่าจัดส่ง</span>
                                        <span class="text-dark fs-6">฿100.00</span>
                                    </div>
                                    <div class="d-flex justify-content-between">
                                        <span class="text-muted">ยอดรวมทั้งสิ้น </span>
                                        <span class="text-dark fs-6">฿23,100.00</span>
                                    </div>
                                    <div class="d-flex justify-content-end  mb-4">
                                        <span class="text-dark fs-6">รวมภาษีมูลค่าเพิ่ม (ถ้ามี)</span>
                                    </div>
                                    <rotuer-link to="/user/checkout" class="btn w-100">ดำเนินการชำระเงิน</rotuer-link>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div> -->
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
        setInterval(() => {
            this.loding = false
        }, 500);
    }
}
</script>

<style scoped>
.grid-product {
    display: grid;
    grid-template-columns: auto 1fr 1fr 1fr;
    grid-gap: 10px;
    padding: 10px;
}

.img-product-item {
    width: 80px;
    height: 80px;
    object-fit: cover;
}

.price-product{
    text-align: center;
}
.icon {
    font-size: 18px;
    margin: 0 5px;
    cursor: pointer;
    transition: all 0.3s ease;
}

.option-item .icon:hover {
    color: var(--pink) !important;
}

.input-qty-product {
    width: 60px;
    text-align: center;
    border: 1px solid transparent;
    transition: border 0.3s ease;
    outline: none;
    padding: 6px 12px;
}

.input-qty-product:focus {
    border: 1px solid var(--pink);
}

.btn-quantity {
    border: 0;
    outline: none;
    padding: 6px 12px;
    transition: all 0.3s ease;
    border-radius: 0 1px 1px 0;
}

.btn-quantity:hover {
    background-color: var(--pink) !important;
    color: #fff;
}

.text-vat{
    font-size: 12px;
}
.text-title-row-cart{
    font-size: 14px;
}

.text-title-cart{
    font-size: 18px;
    font-weight: 500;
}

@media screen and (max-width:992px) {
    .grid-product {
        grid-template-columns: auto auto;
    }
    .body{
        background: red !important;
    }
    .price-product{
    text-align: left;
}
}
</style>
<template>
    <div>
        <Loading v-if="loading"/>
        <div class="row">
            <div class="col-12">
                <BreadCrumb />
                <div class="card">
                    <div class="card-body">
                        <div class="row g-3">
                            <div class="col-md-5 col-lg-4 order-last">
                                <div class="form-result-order">
                                    <h4 class="d-flex justify-content-start align-items-center mb-3">
                                        <span class="text-body-secondary text-checkout">สรุปข้อมูลคำสั่งซื้อ</span>
                                    </h4>
                                    <ul class="list-group mb-3">
                                        <li class="list-group-item d-flex justify-content-between lh-sm">
                                            <div>
                                                <h6 class="my-0">Casio A10210</h6>
                                            </div>
                                            <span class="text-body-secondary">฿2,000.00</span>
                                        </li>
                                        <li class="list-group-item d-flex justify-content-between bg-body-tertiary">
                                            <div class="text-muted">
                                                <small>ยอดรวม (1 ชิ้น)</small>
                                            </div>
                                            <span class="text-muted">฿45.00</span>
                                        </li>
                                        <li class="list-group-item d-flex justify-content-between">
                                            <span>ยอดรวมทั้งสิ้น:</span>
                                            <strong class="text-primary mt-0">฿2,045.00</strong>
                                        </li>
                                    </ul>
                                </div>

                                <div class="form-select-pay">
                                    <h4 class="d-flex justify-content-start align-items-center mb-3">
                                        <span class="text-body-secondary text-checkout">เลือกวิธีการชำระเงิน</span>
                                    </h4>

                                    <div :class="`card-pay p-3 rounded mb-3 ${!type_pay ? 'card-pay-checked' : ''}`"
                                        @click="type_pay = false">
                                        <div class="d-flex justify-content-between align-items-center">
                                            <div class="d-flex align-items-center mb-1">
                                                <i class="fa-solid fa-money-bill"></i>
                                                <span style="font-size:14px;" class="ms-2">ชำระเงินปลายทาง</span>
                                            </div>
                                            <input type="radio" name="type" id="" class="form-control-pay"
                                                :checked="!type_pay" @change="type_pay = 2">
                                        </div>
                                        <span style="font-size:12px;" class="text-muted">ชำระเงินเมื่อได้รับสินค้า</span>
                                    </div>
                                    <div :class="`card-pay p-3 rounded ${type_pay ? 'card-pay-checked' : ''}`"
                                        @click="type_pay = true">
                                        <div class="d-flex justify-content-between align-items-center">
                                            <div class="d-flex align-items-center mb-1">
                                                <i class="fa-solid fa-money-bill-transfer"></i>
                                                <span style="font-size:14px;" class="ms-2">โอนธนาคาร</span>
                                            </div>
                                            <input type="radio" name="type" id="" class="form-control-pay"
                                                :checked="type_pay" @change="type_pay = true">
                                        </div>
                                        <span style="font-size:12px;" class="text-muted">โอนชำระส่งสลิปโอนเงิน</span>
                                    </div>
                                    <div :class="cardClasses">
                                        <div v-for="i in 3" :key="i"
                                            :class="`border-bottom ${i == 3 ? 'border-bottom-0' : ''}`">
                                            <div class="d-flex justify-content-start">
                                                <div class="img-bank me-3">
                                                    <img width="54px" height="54px" style="object-fit:cover;"
                                                        src="https://static.thairath.co.th/media/dFQROr7oWzulq5Fa4L9KDKHA25hRnCIpOmH8dElnYccZRhKzS7FjUbRg43Z8i03cGkx.jpg"
                                                        alt="">
                                                </div>
                                                <div class="text-bank">
                                                    <span style="font-size:14px;" class="d-block">Weeraphong Surapho</span>
                                                    <span style="font-size:12px;">7892379823</span>
                                                </div>
                                            </div>
                                        </div>
                                        <div class="mt-1">
                                            <input type="file" class="form-control-sm fs-6">
                                        </div>
                                    </div>
                                </div>

                                <div class="mt-3">
                                    <button class="btn w-100">สั่งซื้อ</button>
                                </div>
                            </div>

                            <div class="col-md-7 col-lg-8 order-first">
                                <h4 class="mb-3">Shipping Address</h4>
                                <form class="needs-validation" novalidate @submit.prevent="validateForm" ref="myForm">
                                    <div class="row g-3">
                                        <div class="col-sm-6">
                                            <label for="firstName" class="form-label">ชื่อ - สกุล</label>
                                            <input type="text" class="" id="firstName" placeholder="" value="" required="">
                                            <div class="invalid-feedback">
                                                يرجى إدخال اسم أول صحيح.
                                            </div>
                                        </div>

                                        <div class="col-sm-6">
                                            <label for="lastName" class="form-label">ที่อยู่</label>
                                            <input type="text" class="" id="lastName" placeholder="" value="" required="">
                                            <div class="invalid-feedback">
                                                يرجى إدخال اسم عائلة صحيح.
                                            </div>
                                        </div>
                                        <div class="col-sm-6">
                                            <label for="lastName" class="form-label">หมายเลขโทรศัพท์</label>
                                            <input type="text" class="" id="lastName" placeholder="" value="" required="">
                                            <div class="invalid-feedback">
                                                يرجى إدخال اسم عائلة صحيح.
                                            </div>
                                        </div>

                                        <div class="col-sm-6">
                                            <label for="lastName" class="form-label">จังหวัด</label>
                                            <select name="" id="">
                                                <option value="" disabled selected>กรุณาเลือกจังหวัด</option>
                                            </select>
                                            <div class="invalid-feedback">
                                                يرجى إدخال اسم عائلة صحيح.
                                            </div>
                                        </div>

                                        <div class="col-sm-6 ">
                                            <label for="lastName" class="form-label">จังหวัด</label>
                                            <select name="" id="">
                                                <option value="" disabled selected>กรุณาเลือกจังหวัด</option>
                                            </select>
                                            <div class="invalid-feedback">
                                                يرجى إدخال اسم عائلة صحيح.
                                            </div>
                                        </div>
                                        <div class="col-sm-6 ">
                                            <label for="lastName" class="form-label">เขต/อำเภอ</label>
                                            <select name="" id="">
                                                <option value="" disabled selected>กรุณาเลือกเขต/อำเภอ</option>
                                            </select>
                                            <div class="invalid-feedback">
                                                يرجى إدخال اسم عائلة صحيح.
                                            </div>
                                        </div>
                                        <div class="col-sm-6 ">
                                            <label for="lastName" class="form-label">รหัสไปรษณีย์</label>
                                            <select name="" id="">
                                                <option value="" disabled selected>กรุณาระบุรหัสไปรษณีย์</option>
                                            </select>
                                            <div class="invalid-feedback">
                                                يرجى إدخال اسم عائلة صحيح.
                                            </div>
                                        </div>
                                    </div>
                                    <hr class=" d-block d-lg-none">
                                    <!-- <button class="w-100 btn btn-primary btn-lg mt-3" type="submit">الاستمرار
                                        بالدفع</button> -->
                                </form>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            type_pay: true,
            loading: false
        }
    },
    methods: {
        validateForm(event) {
            const form = this.$refs.myForm;

            if (!form.checkValidity()) {
                event.stopPropagation();
            }

            form.classList.add('was-validated');
        },
        start() {
            this.loading = true
        },
        finish() {
            this.loading = false
        }
    },
    computed: {
        cardClasses() {
            return {
                'p-2': true,
                'fade-show-card': true,
                'fade-show-card-show': this.type_pay,
            };
        },
    },
    mounted() {
        this.start()
        setTimeout(() => {
            this.finish()
        }, 500);
    }
}
</script>

<style scoped>
input:not(.form-control-pay),
select {
    width: 100%;
    border: 1px solid #ddd;
    transition: border 0.3s ease;
    outline: none;
    padding: 6px 12px;
}

input:focus,
select:focus {
    border: 1px solid var(--pink);
}

.text-checkout {
    font-size: 18px;
}

.card-pay {
    border: 1px solid #ddd;
    transition: border 0.1s ease;
    cursor: pointer;
}

.card-pay-checked {
    border: 1px solid var(--pink) !important;
}

.fade-show-card {
    opacity: 0;
    height: 0;
    overflow: hidden;
    transition: opacity 0.2s ease, height 0.2s ease;
}

.fade-show-card-show {
    opacity: 1;
    height: auto;
}
</style>
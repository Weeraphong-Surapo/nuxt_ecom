<template>
    <div class=" d-flex justify-content-center align-items-center ">
        <div class="card shadow p-4">
            <div class="logo-img-form px-4 mx-auto" style="margin-bottom:1rem;">
                <img class="" width="105" height="89"
                    src="https://s3.ap-south-1.amazonaws.com/rzp-prod-merchant-assets/payment-link/description/images_DfsP1Y9yXnw1oz.png"
                    alt="">
            </div>
            <div class="form-group mb-3">
                <label for="" class="text-muted">อีเมลผู้ใช้งาน</label>
                <input type="text" name="" id="" aria-describedby="helpId" placeholder="">
            </div>
            <div class="form-group mb-3">
                <label for="" class="text-muted">รหัสผ่าน</label>
                <input type="text" name="" id="" aria-describedby="helpId" placeholder="">
            </div>
            <div>
                <div class="d-flex justify-content-between align-items-start mb-3">
                    <div>
                        <div class="form-check">
                            <input class="form-check-input" type="checkbox" value="" id="">
                            <label class="form-check-label text-muted fs-6">
                                จำฉันไว้
                            </label>
                        </div>
                    </div>
                    <div class="" id="remember-me">
                        <a href="#">ลืมรหัสผ่าน?</a>
                    </div>
                </div>
            </div>
            <button class="btn w-100">เข้าสู่ระบบ</button>
            <div class="d-flex justify-content-center mt-3">
                <span>ยังไม่มีบัญชีเหรอ?&nbsp;</span><router-link to="register">ลงทะเบียน</router-link>
            </div>
        </div>
    </div>
</template>

<script>
import { useStore } from '~/stores/user'

export default {

}
</script>

<style scoped>
input:not([type="checkbox"]) {
    width: 100%;
    border: 1px solid #ddd;
    transition: border 0.3s ease;
    outline: none;
    padding: 6px 12px;
}

input:focus {
    border: 1px solid var(--pink);
}
</style>
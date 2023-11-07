<template>
    <nav aria-label="breadcrumb">
        <ol class="breadcrumb">
            <li class="breadcrumb-item"><NuxtLink to="/">หน้าหลัก</NuxtLink></li>
            <li class="breadcrumb-item"><NuxtLink to="/products">สินค้าทั้งหมด</NuxtLink></li>
            <li class="breadcrumb-item active" aria-current="page">{{ productName }}</li>
        </ol>
    </nav>
</template>

<script>
export default {
    props:['productName']
}
</script>

<style lang="scss" scoped></style>
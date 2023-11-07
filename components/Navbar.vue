<template>
    <div>
        <nav class="navbar navbar-expand-lg navbar-light bg-white py-3 fixed-top">
            <div class="container">
                <router-link to="/" class="navbar-brand order-lg-0 d-flex justify-content-between align-items-center"><img
                        width="60px"
                        src="https://s3.ap-south-1.amazonaws.com/rzp-prod-merchant-assets/payment-link/description/images_DfsP1Y9yXnw1oz.png"
                        alt="">
                    <span class="ms-2">Bigshop</span></router-link>

                <div class="order-lg-2">
                    <router-link :to="menu.path" class="btn btn-nav position-relative"
                        v-for="(menu, index) in menuNavMiddle" :key="index">
                        <i :class="menu.icon"></i>
                        <span class="position-absolute top-0 start-100 badge bg-primary translate-middle">5</span>
                    </router-link>

                    <NuxtLink to="/auth/login" class="btn btn-nav">เข้าสู่ระบบ</NuxtLink>
                    <NuxtLink to="/auth/register" class="btn btn-sign-up">สมัคสมาชิก</NuxtLink>
                </div>
                <button class="navbar-toggler d-lg-none border-0" type="button" data-toggle="collapse"
                    data-target="#collapsibleNavId">
                    <span class="navbar-toggler-icon"></span>
                </button>

                <div class="collapse navbar-collapse order-lg-1" id="collapsibleNavId">
                    <ul class="navbar-nav mx-auto text-center">
                        <li :class="`nav-item px-2 py-2 ${index === menuNavs.length - 1 ? 'border-bottom-0' : ''}`"
                            v-for="(menuNav, index) in menuNavs" :key="index">
                            <router-link :to="menuNav.path" class="nav-link active fs-6 text-uppercase">{{
                                menuNav.title
                            }}</router-link>
                        </li>
                    </ul>
                </div>
            </div>

        </nav>
    </div>
</template>

<script>
export default {
    data() {
        return {
            menuNavs: [{
                path: '/',
                title: 'หน้าหลัก'
            }, {
                path: '/products',
                title: 'สินค้าทั้งหมด'
            }, {
                path: '/about',
                title: 'เกี่ยวกับเรา'
            }, {
                path: '/blogs',
                title: 'บทความ'
            }, {
                path: '/contact',
                title: 'ติดต่อเรา'
            },
            ],
            menuNavMiddle: [
                {
                    path: '/user/carts',
                    icon: 'fa fa-shopping-cart'
                }, {
                    path: '/',
                    icon: 'fa fa-heart'
                }
            ]
        }
    }
}
</script>

<style scoped>
.navbar {
    box-shadow: 0 2px 9px 3px rgba(0, 0, 0, 0.1);
}

.nav-item {
    border-bottom: 0.5px solid rgba(0, 0, 0, 0.05);
}

.nav-link:hover {
    color: var(--pink) !important;
}

.nuxt-link-exact-active {
    color: var(--pink) !important;
}

.btn-sign-up:hover {
    color: white;
}

.btn-sign-up.nuxt-link-exact-active {
    background: var(--pink);
    color: white !important;
}



@media (min-width: 992px) {
    .nav-item {
        border-bottom: none;
    }
}
</style>
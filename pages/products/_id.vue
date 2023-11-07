<template>
    <div>
        <BreadCrumb :productName="id" />


        <div class="card">
            <div class="card-body">


                <div class="row g-5">
                    <template v-if="loding">
                        <div class="col-md-5">
                            <svg class="bd-placeholder-img" width="100%" height="96" xmlns="http://www.w3.org/2000/svg"
                                aria-hidden="true" preserveAspectRatio="xMidYMid slice" focusable="false">
                                <rect width="100%" height="100%" fill="#777"></rect>
                            </svg>
                        </div>
                        <div class="col-md-7">
                            <h5 class="placeholder-glow">
                                <span class="placeholder col-6"></span>
                            </h5>
                            <p class="placeholder-glow">
                                <span class="placeholder col-7"></span>
                                <span class="placeholder col-4"></span>
                                <span class="placeholder col-4"></span>
                                <span class="placeholder col-6"></span>
                                <span class="placeholder col-8"></span>
                            </p>

                        </div>
                    </template>
                    <template v-else>
                        <div class="col-md-5">
                            <div class="position-sticky">
                                <div class="p-4 mb-3 bg-body-tertiary rounded">
                                    <img class="img-fluid mb-2" :src="img_product"
                                        style="height: 410px;width:420px;overflow:hidden;" alt="">
                                    <div id="carouselExampleAutoplaying" class="carousel slide" data-bs-ride="carousel"
                                        v-if="groupedImages">
                                        <div class="carousel-inner">

                                            <div class="carousel-item active" v-for="(imageSet, index) in groupedImages"
                                                :key="index">
                                                <div class="row">
                                                    <div class="col" v-for="(img, imgIndex) in imageSet" :key="imgIndex">
                                                        <img @click="showImg(img)" :src="img" class="img-show-carosusel"
                                                            alt="">
                                                    </div>
                                                </div>
                                            </div>
                                        </div>

                                        <button class="carousel-control-prev" type="button"
                                            data-bs-target="#carouselExampleAutoplaying" data-bs-slide="prev">
                                            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                                            <span class="visually-hidden">Previous</span>
                                        </button>
                                        <button class="carousel-control-next" type="button"
                                            data-bs-target="#carouselExampleAutoplaying" data-bs-slide="next">
                                            <span class="carousel-control-next-icon" aria-hidden="true"></span>
                                            <span class="visually-hidden">Next</span>
                                        </button>
                                    </div>

                                </div>
                            </div>
                        </div>
                        <div class="col-md-7">
                            <h3 class="pb-4 mb-4 fst-italic border-bottom">
                                من Firehose
                            </h3>

                            <article class="blog-post">

                            </article>

                            <article class="blog-post">
                                <h2 class="display-5 link-body-emphasis mb-1">ميزة جديدة</h2>
                                <p class="blog-post-meta">14 ديسمبر 2020 بواسطة <a href="#">Jacob</a></p>

                                <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Soluta assumenda sint
                                    voluptate,
                                    magnam quos cumque minus iste eos dolorum aperiam, quidem tempora ipsam? Soluta possimus
                                    fugit laborum, obcaecati facere quisquam?</p>
                                <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Soluta assumenda sint
                                    voluptate,
                                    magnam quos cumque minus iste eos dolorum aperiam, quidem tempora ipsam? Soluta possimus
                                    fugit laborum, obcaecati facere quisquam?</p>
                                <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Soluta assumenda sint
                                    voluptate,
                                    magnam quos cumque minus iste eos dolorum aperiam, quidem tempora ipsam? Soluta possimus
                                    fugit laborum, obcaecati facere quisquam?</p>
                                <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Soluta assumenda sint
                                    voluptate,
                                    magnam quos cumque minus iste eos dolorum aperiam, quidem tempora ipsam? Soluta possimus
                                    fugit laborum, obcaecati facere quisquam?</p>
                            </article>

                            <nav class="blog-pagination" aria-label="Pagination">
                                <a class="btn btn-outline-primary rounded-pill" href="#">تدوينات أقدم</a>
                                <a class="btn btn-outline-secondary rounded-pill disabled" aria-disabled="true">تدوينات
                                    أحدث</a>
                            </nav>
                        </div>
                    </template>
                </div>
            </div>
        </div>

        <Review />



        <div class="row">
            <div v-for="i in 8" :key="i" class="col-12 col-md-6 col-lg-4 col-xl-3 p-2 gx-0 gy-3">
                <ProductCard :product="i" />
            </div>
        </div>
    </div>
</template>

<script>
export default {
    computed: {
        groupedImages() {
            const groupSize = 5; // Group images in sets of 3
            const grouped = [];
            let currentIndex = 0;

            // Group the remaining images in sets of 3
            for (; currentIndex < this.sub_img.length; currentIndex += groupSize) {
                grouped.push(this.sub_img.slice(currentIndex, currentIndex + groupSize));
            }

            return grouped;
        }
    },
    data() {

        return {
            id: this.$route.params.id,
            sub_img: [
                'https://store.storeimages.cdn-apple.com/8756/as-images.apple.com/is/iphone-15-pro-finish-select-202309-6-7inch-naturaltitanium?wid=5120&hei=2880&fmt=p-jpg&qlt=80&.v=1692845702708',
                'https://media-cdn.bnn.in.th/234715/iPhone_14_Purple_PDP_Image_Position-1A_Purple_1-square_medium.jpg',
                'https://s.isanook.com/hi/0/ud/317/1588167/batch_apple-iphone-15-lineup-_2.jpg?ip/resize/w728/q80/jpg',
                'https://media.studio7thailand.com/75767/iPhone_14_Pro_Max_Deep_Purple_PDP_Image_Position-1A_Deep_Purple_1-square_medium.jpg',
                'https://promotions.co.th/wp-content/uploads/2022/09/iphone14-pro-max.jpg',
                'https://store.storeimages.cdn-apple.com/8756/as-images.apple.com/is/iphone-15-pro-finish-select-202309-6-7inch-naturaltitanium?wid=5120&hei=2880&fmt=p-jpg&qlt=80&.v=1692845702708',
                'https://media-cdn.bnn.in.th/234715/iPhone_14_Purple_PDP_Image_Position-1A_Purple_1-square_medium.jpg',
                'https://s.isanook.com/hi/0/ud/317/1588167/batch_apple-iphone-15-lineup-_2.jpg?ip/resize/w728/q80/jpg',
                'https://media.studio7thailand.com/75767/iPhone_14_Pro_Max_Deep_Purple_PDP_Image_Position-1A_Deep_Purple_1-square_medium.jpg',
                'https://promotions.co.th/wp-content/uploads/2022/09/iphone14-pro-max.jpg',
            ],
            loding: true,
            img_product: "https://store.storeimages.cdn-apple.com/8756/as-images.apple.com/is/MT223?wid=1144&hei=1144&fmt=jpeg&qlt=90&.v=1693248280978"
        }
    },
    methods: {
        showImg(img) {
            this.img_product = img
        }
    },
    mounted() {
        setTimeout(() => {
            this.loding = false
        }, 500);
    }
}
</script>

<style scoped>
.carousel-row {
    clear: both;
}

.img-show-carosusel {
    width: 70px;
    height: 70px;
    min-width: 50px;
    min-height: 50px;
    margin: auto;
    border: 1px solid rgb(85, 85, 85);
}
</style>
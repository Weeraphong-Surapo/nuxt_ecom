<template>
    <footer class="bg-white py-5 mt-5">
        <div class="container">
            <div class="row text-dark g-4">
                <div class="col-md-6 col-lg-3">
                    <a href="#" class="text-uppercase text-decoration-none brand text-dark">
                        Bigshop
                    </a>
                    <p class="text-dark text-muted mt-3">Lorem ipsum dolor sit amet consectetur adipisicing elit. Praesentium, iure! Rerum nesciunt sit temporibus quaerat quibusdam quisquam velit, laboriosam expedita nisi rem animi quod saepe magnam natus debitis adipisci! Itaque!</p>
                </div>
                <div class="col-md-6 col-lg-3">
                    <h5 class="fw-light">Links</h5>
                    <ul class="list-unstyled">
                        <li class="my-3">
                            <a href="" class="text-dark text-decoration-none text-muted">
                                <i class="fas fa-chevron-right me-1"></i>
                                หน้าหลัก
                            </a>
                        </li>
                        <li class="my-3">
                            <a href="" class="text-dark text-decoration-none text-muted">
                                <i class="fas fa-chevron-right me-1"></i>
                                สินค้าทั้งหมด
                            </a>
                        </li>
                        <li class="my-3">
                            <a href="" class="text-dark text-decoration-none text-muted">
                                <i class="fas fa-chevron-right me-1"></i>
                                เกี่ยวกับเรา
                            </a>
                        </li>
                        <li class="my-3">
                            <a href="" class="text-dark text-decoration-none text-muted">
                                <i class="fas fa-chevron-right me-1"></i>
                                บริการ
                            </a>
                        </li>
                        <li class="my-3">
                            <a href="" class="text-dark text-decoration-none text-muted">
                                <i class="fas fa-chevron-right me-1"></i>
                                ติดต่อเรา
                            </a>
                        </li>
                    </ul>
                </div>

                <div class="col-lg-3 col-md-6">
                    <h5 class="fw-light mb-3">Contact Us</h5>
                    <div class="d-flex justify-content-start align-items-start my-2 text-muted">
                        <span class="me-3">
                            <i class="fas fa-map-marked-alt"></i>
                        </span>
                        <span class="fw-light">
                            Albert Street, New York
                        </span>
                    </div>
                    <div class="d-flex justify-content-start align-items-start my-2 text-muted">
                        <span class="me-3">
                            <i class="fa-solid fa-envelope"></i>
                        </span>
                        <span class="fw-light">
                            weerapohong61045@gmail.com
                        </span>
                    </div>
                    <div class="d-flex justify-content-start align-items-start my-2 text-muted">
                        <span class="me-3">
                            <i class="fas fa-phone-alt"></i>
                        </span>
                        <span class="fw-light">
                            092-556-2767
                        </span>
                    </div>
                </div>

                <div class="col-md-6 col-lg-3">
                    <h5 class="fw-light mb-3">Follow me</h5>
                    <div class="d-flex">
                        <ul class="list-unstyled">
                            <li>
                                <a href="" class="text-dark text-decoration-none text-muted">
                                    <i class="fa-brands fa-facebook"></i>
                                </a>
                            </li>
                            <li>
                                <a href="" class="text-dark text-decoration-none text-muted">
                                    <i class="fa-brands fa-twitter"></i>
                                </a>
                            </li>
                            <li>
                                <a href="" class="text-dark text-decoration-none text-muted">
                                    <i class="fa-brands fa-instagram"></i>
                                </a>
                            </li>
                            <li>
                                <a href="" class="text-dark text-decoration-none text-muted">
                                    <i class="fa-brands fa-pinterest"></i>
                                </a>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>

<script>
    export default {
        
    }
</script>

<style  scoped>
footer .brand{
    letter-spacing: 2px;
}

footer a{
    transition:color 0.3s ease;
}

footer a:hover{
    color:var(--pink) !important;
}
</style>
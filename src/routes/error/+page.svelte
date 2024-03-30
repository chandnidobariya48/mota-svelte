<script>
    import { Row } from "@sveltestrap/sveltestrap";
    import ErrorImage from '../../../src/assets/images/error.png';
    import Image from '../../../src/assets/images/logo-icon-48.png';
</script>
<section class="position-relative bg-soft-primary">
    <div class="container-fluid">
        <Row>
            <div class="col-12 p-0">
                <div class="d-flex flex-column min-vh-100 justify-content-center px-md-5 py-5 px-4">
                    <div class="text-center">
                        <a href={null}><img src={Image} alt="" /></a>
                    </div>
                    <div class="title-heading text-center my-auto">
                        <img src={ErrorImage} class="img-fluid" alt="" />
                        <h1 class="mb-3 mt-5 text-dark">Page Not Found?</h1>
                        <p class="text-muted">Whoops, this is embarassing. <br /> Looks like the page you were looking for wasn't found.</p>

                        <div class="mt-4">
                            <a href="/" class="back-button btn btn-primary">Back to Home</a>
                        </div>
                    </div>
                    <div class="text-center">
                        <p class="mb-0 text-muted">© {(new Date().getFullYear())}{" "} Motos. Design with <i class="mdi mdi-heart text-danger"></i> by <a href={null} class="text-reset">Shreethemes</a>.</p>
                    </div>
                </div>
            </div>
        </Row>
    </div>
</section>
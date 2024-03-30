<script>
    import { Row } from "@sveltestrap/sveltestrap";
    import Icon from '../../../assets/images/logo-icon-64.png';
</script>

<section class="position-relative">
    <div class="bg-video-wrapper">
        <iframe src="https://player.vimeo.com/video/187372244?background=1&autoplay=1&loop=1&byline=0&title=0" title="vimeo-video"></iframe>
    </div>
    <div class="bg-overlay"></div>
    <div class="container-fluid">
        <Row>
            <div class="col-12 p-0">
                <div class="d-flex flex-column min-vh-100 justify-content-center px-md-5 py-5 px-4">
                    <div class="text-center mt-md-5">
                        <a href="/"><img src={Icon} alt="" /></a>
                    </div>
                    <div class="title-heading text-center my-auto">
                        <h4 class="coming-soon fw-bold display-3 text-white text-uppercase">Coming Soon</h4>
                        <p class="text-white-50 para-desc mx-auto mb-0">Our design projects are fresh and simple and will benefit your business greatly. Learn more about our work!</p>

                        <div class="subcribe-form mt-4 pt-2">
                            <form action="page-comingsoon.html">
                                <input type="email" id="email" class="bg-white opacity-6 rounded shadow" required placeholder="Type your Email.." />
                                <button type="submit" class="btn btn-primary" style={{ top: '2.5px' }}>Notify Me</button>
                            </form>
                        </div>

                        <p class="text-white-50 mt-2"><span class="text-danger fw-bold">*</span>Notify me when website is launched</p>
                    </div>
                    <div class="text-center mb-md-5 footer">
                        <p class="mb-0 text-reset">© {(new Date().getFullYear())}{" "} Motos. Design with <i class="mdi mdi-heart text-danger"></i> by <a href="/" class="text-reset">Shreethemes</a>.</p>
                    </div>
                </div>
            </div>
        </Row>
    </div>
</section>
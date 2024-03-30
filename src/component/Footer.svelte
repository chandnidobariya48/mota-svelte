<script>
    import { onMount } from 'svelte';
    import { Col, Container, Card, Row } from '@sveltestrap/sveltestrap';
    import { ArrowUpIcon } from 'svelte-feather-icons';
    import Logo from "../assets/images/logo-icon-32.png";

    let scroll = false;
    onMount(() => {
        window.addEventListener("scroll", () => {
            scroll = window.scrollY > 50;
        });
    });

    const scrollTop = () =>{
    window.scrollTo({ 
        top: 0,  
        behavior: 'smooth'
        });
    }
</script>
<a href="/#" on:click={()=>scrollTop()} id="back-to-top" class={`back-to-top rounded-pill fs-5 ${scroll ? 'd-block' : 'hidden' }`}><ArrowUpIcon class="fea icon-sm icons align-middle" /></a>

<footer class="bg-footer">
    <Container>
        <Row class="justify-content-center">
            <div class="col-12">
                <div class="footer-py-60 text-center">
                    <Row class="py-5">
                        <Col md={4} >
                            <Card class="border-0 text-center features feature-primary bg-transparent">
                                <div class="feature-icon text-center mx-auto">
                                    <i class="uil uil-phone rounded h4 mb-0"></i>
                                </div>
                                <div class="content mt-4">
                                    <h5 class="footer-head">Phone</h5>
                                    <p class="text-muted">Start working with Motos that can provide everything</p>
                                    <a href="tel:+152534-468-854" class="text-foot">+152 534-468-854</a>
                                </div>
                            </Card>
                        </Col>

                        <Col md={4} class="mt-4 mt-sm-0 pt-2 pt-sm-0">
                            <Card class="border-0 text-center features feature-primary bg-transparent">
                                <div class="feature-icon text-center mx-auto">
                                    <i class="uil uil-envelope rounded h4 mb-0"></i>
                                </div>
                                <div class="content mt-4">
                                    <h5 class="footer-head">Email</h5>
                                    <p class="text-muted">Start working with Motos that can provide everything</p>
                                    <a href="mailto:contact@example.com" class="text-foot">contact@example.com</a>
                                </div>
                            </Card>
                        </Col>

                        <Col md={4} class="mt-4 mt-sm-0 pt-2 pt-sm-0">
                            <Card class="border-0 text-center features feature-primary bg-transparent">
                                <div class="feature-icon text-center mx-auto">
                                    <i class="uil uil-map-marker rounded h4 mb-0"></i>
                                </div>
                                <div class="content mt-4">
                                    <h5 class="footer-head">Location</h5>
                                    <p class="text-muted">C/54 Northwest Freeway, Suite 558, <br />Houston, USA 485</p>
                                    <a href="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d39206.002432144705!2d-95.4973981212445!3d29.709510002925988!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8640c16de81f3ca5%3A0xf43e0b60ae539ac9!2sGerald+D.+Hines+Waterwall+Park!5e0!3m2!1sen!2sin!4v1566305861440!5m2!1sen!2sin"
                                        data-type="iframe" class="video-play-icon text-foot lightbox">View on Google map</a>
                                </div>
                            </Card>
                        </Col>
                    </Row>
                </div>
            </div>
        </Row>
    </Container>

    <div class="footer-py-30 footer-bar bg-footer">
        <Container class="text-center">
            <Row class="align-items-center justify-content-between">
                <Col lg={3} md={2} sm={3}>
                    <div class="text-sm-start">
                        <a href="/" class="logo-footer">
                            <img src={Logo} alt="" />
                        </a>
                    </div>
                </Col>

                <Col lg={6} md={6} sm={6} class="mt-4 mt-sm-0 pt-2 pt-sm-0">
                    <ul class="list-unstyled footer-list terms-service mb-0">
                        <li class="list-inline-item mb-0"><a href="/" class="text-foot me-2">Privacy</a></li>
                        <li class="list-inline-item mb-0"><a href="/" class="text-foot me-2">Terms</a></li>
                        <li class="list-inline-item mb-0"><a href="/" class="text-foot me-2">FAQs</a></li>
                        <li class="list-inline-item mb-0"><a href="/" class="text-foot">Contact</a></li>
                    </ul>
                </Col>

                <Col lg={3} md={4} sm={3} class="mt-4 mt-sm-0 pt-2 pt-sm-0">
                    <div class="text-sm-end">
                        <p class="mb-0 text-foot">© {(new Date().getFullYear())}{" "} <a href="/" class="text-reset">Shreethemes</a>.</p>
                    </div>
                </Col>
            </Row>
        </Container>
    </div>
</footer>
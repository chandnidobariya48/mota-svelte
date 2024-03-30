<script>
    import { Col, Container, Row } from '@sveltestrap/sveltestrap';
</script>
<section class="section" id="contact">
    <Container>
        <Row class="justify-content-center">
            <Col>
                <div class="section-title text-center mb-4 pb-2">
                    <h4 class="title mb-3">Get In Touch !</h4>
                    <p class="text-muted para-desc mb-0 mx-auto">Launch your campaign and benefit from our expertise on designing and managing conversion centered bootstrap v5 html page.</p>
                </div>
            </Col>
        </Row>

        <Row class="align-items-center">
            <Col lg={8} md={6} class="order-md-2 order-1 mt-4 pt-2">
                <div class="p-4 rounded shadow bg-white">
                    <form method="post" name="myForm">
                        <p class="mb-0" id="error-msg"></p>
                        <div id="simple-msg"></div>
                        <Row>
                            <Col md={6}>
                                <div class="mb-4">
                                    <input name="name" id="name" type="text" class="form-control" placeholder="Name :" />
                                </div>
                            </Col>

                            <Col md={6} >
                                <div class="mb-4">
                                    <input name="email" id="email" type="email" class="form-control" placeholder="Email :" />
                                </div>
                            </Col>

                            <div class="col-12">
                                <div class="mb-4">
                                    <input name="subject" id="subject" class="form-control" placeholder="Subject :" />
                                </div>
                            </div>

                            <div class="col-12">
                                <div class="mb-4">
                                    <textarea name="comments" id="comments" rows={4} class="form-control" placeholder="Message :"></textarea>
                                </div>
                            </div>
                        </Row>
                        <Row>
                            <div class="col-12 text-end">
                                <button type="submit" id="submit" name="send" class="btn btn-primary">Send Message</button>
                            </div>
                        </Row>
                    </form>
                </div>
            </Col>

            <Col lg={4} md={6} class="col-12 order-md-1 order-2 mt-4 pt-2">
                <div class="me-lg-4">
                    <div class="d-flex">
                        <div class="icons text-center mx-auto">
                            <i class="uil uil-phone d-block rounded h4 mb-0"></i>
                        </div>

                        <div class="flex-1 ms-3">
                            <h5 class="mb-2">Phone</h5>
                            <a href="tel:+152534-468-854" class="text-muted">+152 534-468-854</a>
                        </div>
                    </div>

                    <div class="d-flex mt-4">
                        <div class="icons text-center mx-auto">
                            <i class="uil uil-envelope d-block rounded h4 mb-0"></i>
                        </div>

                        <div class="flex-1 ms-3">
                            <h5 class="mb-2">Email</h5>
                            <a href="mailto:contact@example.com" class="text-muted">contact@example.com</a>
                        </div>
                    </div>

                    <div class="d-flex mt-4">
                        <div class="icons text-center mx-auto">
                            <i class="uil uil-map-marker d-block rounded h4 mb-0"></i>
                        </div>

                        <div class="flex-1 ms-3">
                            <h5 class="mb-2">Location</h5>
                            <p class="text-muted mb-2">C/54 Northwest Freeway, Suite 558, Houston, USA 485</p>
                        </div>
                    </div>
                </div>
            </Col>
        </Row>
    </Container>
</section>
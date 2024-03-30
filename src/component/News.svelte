<script>
import { Col, Container, Card, Row, CardBody } from '@sveltestrap/sveltestrap';

import Blo1Image from "../assets/images/blog/1.jpg";
import Blo2Image from "../assets/images/blog/2.jpg";
import Blo3Image from "../assets/images/blog/3.jpg";
</script>
<section class="section bg-light" id="blog">
    <Container>
        <Row class="justify-content-center">
            <Col>
                <div class="section-title text-center mb-4 pb-2">
                    <h4 class="title mb-3">Latest News</h4>
                    <p class="text-muted para-desc mb-0 mx-auto">Launch your campaign and benefit from our expertise on designing and managing conversion centered bootstrap v5 html page.</p>
                </div>
            </Col>
        </Row>

        <Row>
            <Col lg={4} md={6} class="mt-4 pt-2">
                <Card class="blog blog-primary shadow rounded overflow-hidden border-0">
                    <div class="blog-image position-relative overflow-hidden">
                        <img src={Blo1Image} class="img-fluid" alt="" />
                    </div>

                    <CardBody class="content p-0">
                        <div class="p-4">
                            <a href="/" class="h5 title text-dark d-block mb-0">Building Your Corporate Identity from Motos</a>
                            <p class="text-muted mt-2 mb-0">The most well-known dummy text is the 'Lorem Ipsum', in the 16th century.</p>

                            <div class="mt-3">
                                <a href="/" class="link text-dark">Read More <i class="uil uil-arrow-right"></i></a>
                            </div>
                        </div>
                    </CardBody>
                </Card>
            </Col>

            <Col lg={4} md={6} class="mt-4 pt-2">
                <Card class="blog blog-primary shadow rounded overflow-hidden border-0">
                    <div class="blog-image position-relative overflow-hidden">
                        <img src={Blo2Image} class="img-fluid" alt="" />
                    </div>

                    <CardBody class="content p-0">
                        <div class="p-4">
                            <a href="/" class="h5 title text-dark d-block mb-0">The Dark Side of Overnight Success</a>
                            <p class="text-muted mt-2 mb-0">The most well-known dummy text is the 'Lorem Ipsum', in the 16th century.</p>

                            <div class="mt-3">
                                <a href="/" class="link text-dark">Read More <i class="uil uil-arrow-right"></i></a>
                            </div>
                        </div>
                    </CardBody>
                </Card>
            </Col>

            <Col lg={4} md={6} class="mt-4 pt-2">
                <Card class="blog blog-primary shadow rounded overflow-hidden border-0">
                    <div class="blog-image position-relative overflow-hidden">
                        <img src={Blo3Image} class="img-fluid" alt="" />
                    </div>

                    <CardBody class="content p-0">
                        <div class="p-4">
                            <a href="/" class="h5 title text-dark d-block mb-0">The Right Hand of Business IT World</a>
                            <p class="text-muted mt-2 mb-0">The most well-known dummy text is the 'Lorem Ipsum', in the 16th century.</p>

                            <div class="mt-3">
                                <a href="/" class="link text-dark">Read More <i class="uil uil-arrow-right"></i></a>
                            </div>
                        </div>
                    </CardBody>
                </Card>
            </Col>
        </Row>
    </Container>
</section>
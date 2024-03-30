<script>
import { Col, Container, Card, Row } from '@sveltestrap/sveltestrap';

const pricing = [
    {
        id: 1,
        title: 'Free',
        price: 0,
        features: ['1 Domains', '1 GB File upload', '2 GB Secure storage', 'Unlimited bandwidth']
    },
    {
        id: 2,
        title: 'Startups',
        price: 9,
        features: ['5 Domains', '2 GB File upload', '20 GB Secure storage', 'Unlimited bandwidth']
    },
    {
        id: 3,
        title: 'Business',
        price: 39,
        features: ['10 Domains', '5 GB File upload', '50 GB Secure storage', 'Unlimited bandwidth']
    },
    {
        id: 4,
        title: 'Premium',
        price: 99,
        features: ['50 Domains', '10 GB File upload', '200 GB Secure storage', 'Unlimited bandwidth']
    }
];
</script>
<section class="section bg-light" id="pricing">
    <Container>
        <Row class="justify-content-center">
            <div class="col-12">
                <div class="section-title text-center mb-4 pb-2">
                    <h4 class="title fw-semibold mb-4">Pricing Plans</h4>
                    <p class="para-desc text-muted mx-auto mb-0">Launch your campaign and benefit from our expertise on designing and managing conversion centered bootstrap v5 html page.</p>
                </div>
            </div>
        </Row>

        <Row>
            {#each pricing as item}
                <Col lg={3} md={6} class="col-12 mt-4 pt-2">
                    <Card class="border-0 shadow">
                        <div class="p-4 border-bottom border-light">
                            <h6 class="fw-semibold mb-3 text-uppercase">{item.title}</h6>
                            <p class="text-muted mb-0">For individuals looking for a simple Startups solution</p>

                            <div class="d-flex my-4">
                                <span class="price h3 fw-semibold mb-0">${item.price}</span>
                                <span class="text-muted align-self-end mb-1">/mo</span>
                            </div>

                            <a href="/" class="btn btn-primary w-100">Buy Now</a>
                        </div>

                        <div class="p-4">
                            <h6 class="mb-3">Features:</h6>
                            <ul class="mb-0 list-unstyled">
                                {#each item.features as subitem,subkey}
                                    <li class="text-muted "><span class={item.price < 90 && subkey > 2 ? "text-danger h5 me-1" : ' text-success h5 me-1'}><i class={item.price < 90 && subkey > 2 ? "uil uil-times-circle align-middle" : ' uil uil-check-circle align-middle'}></i></span> {subitem}</li>
                                {/each}
                            </ul>
                        </div>
                    </Card>
                </Col>
            {/each}
            <div class="col text-center mt-2">
                <p class="mt-3 mb-0 text-muted">Note: <span class="text-danger fs-5">*</span>No credit card required</p>
            </div>
        </Row>
    </Container>
</section>
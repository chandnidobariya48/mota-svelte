<script>
import { Col, Container, Row } from '@sveltestrap/sveltestrap';
import { Splide, SplideSlide } from '@splidejs/svelte-splide';
// Default theme
import '@splidejs/svelte-splide/css';

// or only core styles
import '@splidejs/svelte-splide/css/core';

import avatar1 from "../assets/images/client/01.jpg";
import avatar2 from "../assets/images/client/02.jpg";
import avatar3 from "../assets/images/client/03.jpg";
import avatar4 from "../assets/images/client/04.jpg";
import avatar5 from "../assets/images/client/05.jpg";

import Map from "../assets/images/map.png";
const settings = {
    arrows: false,
    mouseDrag: true,
    loop: true,
    rewind: true,
    autoplay: true,
    autoplayButtonOutput: false,
    autoplayTimeout: 3000,
    navPosition: "bottom",
    speed: 400,
    perPage : 3,
    gap    : 12,
    classes: {
		page      : 'splide__pagination__page',
    },
    breakpoints: {
        992: {
            perPage: 3
        },

        767: {
            perPage: 2
        },

        320: {
            perPage: 1
        },
    },
};

const review = [
        {
            id: '1',
            profile: avatar1,
            name: 'Calvin Carlo',
            designation: "Manager",
            description: "According to most sources, Lorum Ipsum can be traced back to a text composed by Cicero Launch your campaign and benefit from our expertise."
        },
        {
            id: '2',
            profile: avatar2,
            name: 'Christa Smith',
            designation: "Manager",
            description: "According to most sources, Lorum Ipsum can be traced back to a text composed by Cicero Launch your campaign and benefit from our expertise."
        }, {
            id: '3',
            profile: avatar3,
            name: 'Jemina CLone',
            designation: "Manager",
            description: "According to most sources, Lorum Ipsum can be traced back to a text composed by Cicero Launch your campaign and benefit from our expertise."
        }, {
            id: '4',
            profile: avatar4,
            name: 'Smith Vodka',
            designation: "Manager",
            description: "According to most sources, Lorum Ipsum can be traced back to a text composed by Cicero Launch your campaign and benefit from our expertise."
        },
        {
            id: '5',
            profile: avatar5,
            name: 'Cristino Murfi',
            designation: "Manager",
            description: "According to most sources, Lorum Ipsum can be traced back to a text composed by Cicero Launch your campaign and benefit from our expertise."
        },
    ];
</script>

<section class="section" id="review">
    <Container>
        <Row class="justify-content-center">
            <div class="col-12">
                <div class="section-title text-center mb-4 pb-2">
                    <h4 class="title mb-3">Happy Client's</h4>
                    <p class="text-muted para-desc mx-auto mb-0">Launch your campaign and benefit from our expertise on designing and managing conversion centered bootstrap5 html page.</p>
                </div>
            </div>
        </Row>

        <Row>
            <div class="col-12 mt-4">
                <div class="tiny-three-item">
                    <Splide options={settings} class="p-0">
                            {#each review as el}
                                <SplideSlide>
                                <div class="customer-testi m-1">
                                    <div class="content p-3 shadow rounded bg-white position-relative">
                                        <ul class="list-unstyled mb-0 text-warning">
                                            <li class="list-inline-item"><i class="mdi mdi-star"></i></li>
                                            <li class="list-inline-item"><i class="mdi mdi-star"></i></li>
                                            <li class="list-inline-item"><i class="mdi mdi-star"></i></li>
                                            <li class="list-inline-item"><i class="mdi mdi-star"></i></li>
                                            <li class="list-inline-item"><i class="mdi mdi-star"></i></li>
                                        </ul>
                                        <p class="text-muted mt-2">" According to most sources, Lorum Ipsum can be traced back to a text composed by Cicero Launch your campaign and benefit from our expertise. "</p>
                                    </div>
                                    <div class="text-center mt-3">
                                        <img src={el.profile} class="avatar avatar-small rounded shadow" alt="" />
                                        <p class="text-primary mt-3 mb-0">{el.name} <small class="text-muted d-block ms-2">{el.designation}</small></p>
                                    </div>
                                </div>
                                </SplideSlide>
                            {/each}
                      </Splide>
                </div>
            </div>
        </Row>
    </Container>

    <Container class="mt-100 mt-60">
        <div class="py-5 px-4 bg-soft-primary rounded-lg" style="background : url('{Map}') center center">
            <Row class="justify-content-center">
                <div class="col-12">
                    <div class="section-title text-center mb-4 pb-2">
                        <h4 class="title mb-4">Subscribe our Newsletter</h4>
                        <p class="text-muted mx-auto para-desc mb-0">Launch your campaign and benefit from our expertise on designing and managing conversion centered bootstrap5 html page.</p>
                    </div>
                </div>

                <Col lg={8}>
                    <div class="text-center subcribe-form mt-4 pt-2">
                        <form>
                            <div class="form-group mb-0">
                                <input type="email" id="email2" name="email" class="rounded-pill" placeholder="Your Email Id" />
                                <button type="submit" class="btn btn-pills btn-primary">Subscribe Now</button>
                            </div>
                        </form>
                    </div>
                </Col>
            </Row>
        </div>
    </Container>

</section>
<script>
    import { Splide, SplideSlide,SplideTrack } from '@splidejs/svelte-splide';
    // Default theme
import '@splidejs/svelte-splide/css';
// or only core styles
import '@splidejs/svelte-splide/css/core';
    import {
        Col, Container, Row, Nav, CardBody, Card,
        NavbarBrand,
        NavbarToggler,
        Collapse,
        NavItem
    } from "@sveltestrap/sveltestrap";
    import Image1 from '../../../assets/images/bg/1.jpg';
    import Image2 from '../../../assets/images/bg/2.jpg';
    import Image3 from '../../../assets/images/bg/3.jpg';
	const options = {
        rewind  : true,
        autoplay: true,
        arrows  : true,
    }
  
</script>
<section class="swiper-slider-hero position-relative d-block vh-100" id="home">
    <div class="swiper-container position-absolute end-0 top-0 w-100 vh-100">
    <Splide  options={ {
        rewind: true,
        autoplay : true,
        perPage: 1,
        interval : 2000,
      } } hasTrack={ false } aria-label="...">
<SplideTrack>
        <SplideSlide class="swiper-slide d-flex align-items-center overflow-hidden w-100 vh-100">
            <div class="slide-inner position-absolute w-100 vh-100 bg-center slide-bg-image d-flex align-items-center" style=" background: url('{Image1}') center center">
                <div class="bg-overlay"></div>
                <Container class="position-relative">
                    <div class="row justify-content-center">
                        <div class="col-12">
                            <div class="title-heading text-center">
                                <h1 class="display-5 text-white title-dark fw-bold mb-4">Business Planning, Strategies <br /> and Execution</h1>
                                <p class="para-desc mx-auto text-white-50">Launch your campaign and benefit from our expertise on designing and managing conversion centered bootstrap v5 html page.</p>

                                <div class="mt-4 pt-2">
                                    <a href={null} class="btn btn-primary">Contact us</a>
                                </div>
                            </div>
                        </div>
                    </div>
                </Container>
            </div>
        </SplideSlide>

        <SplideSlide class="swiper-slide d-flex align-items-center overflow-hidden w-100 vh-100">
            <div class="slide-inner position-absolute w-100 vh-100 bg-center slide-bg-image d-flex align-items-center" style=" background: url('{Image2}') center center">
                <div class="bg-overlay"></div>
                <Container class="position-relative">
                    <div class="row justify-content-center">
                        <div class="col-12">
                            <div class="title-heading text-center">
                                <h1 class="display-5 text-white title-dark fw-bold mb-4">Financial Projections And Analysis <br /> Marketing</h1>
                                <p class="para-desc mx-auto text-white-50">Launch your campaign and benefit from our expertise on designing and managing conversion centered bootstrap v5 html page.</p>

                                <div class="mt-4 pt-2">
                                    <a href={null} class="btn btn-primary">Get Started</a>
                                </div>
                            </div>
                        </div>
                    </div>
                </Container>
            </div>
        </SplideSlide>
        <SplideSlide class="swiper-slide d-flex align-items-center overflow-hidden w-100 vh-100">
            <div class="slide-inner position-absolute w-100 vh-100 bg-center slide-bg-image d-flex align-items-center" style=" background: url('{Image3}') center center">
                <div class="bg-overlay"></div>
                <Container class="position-relative">
                    <div class="row justify-content-center">
                        <div class="col-12">
                            <div class="title-heading text-center">
                                <h1 class="display-5 text-white title-dark fw-bold mb-4">International Business <br /> Opportunities</h1>
                                <p class="para-desc mx-auto text-white-50">Launch your campaign and benefit from our expertise on designing and managing conversion centered bootstrap v5 html page.</p>

                                <div class="mt-4 pt-2">
                                    <a href={null} class="btn btn-primary">Get Started</a>
                                </div>
                            </div>
                        </div>
                    </div>
                </Container>
            </div>
        </SplideSlide>
    </SplideTrack>
    <div class="splide__arrows" />
</Splide>
</div>
</section>
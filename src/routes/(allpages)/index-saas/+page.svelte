<script>
import { onMount } from "svelte";
import { Col, Container, Row } from "@sveltestrap/sveltestrap";

import Navbar from "../../../component/Navbar.svelte";
import Pricing from "../../../component/Pricing.svelte";
import Review from "../../../component/Review.svelte";
import News from "../../../component/News.svelte";
import Contact from "../../../component/Contact.svelte";
import Footer from "../../../component/Footer.svelte";
import Feature from "../../../component/Feature.svelte";

import AmazonImage from '../../../assets/images/client/amazon.svg';
import GoogleImage from '../../../assets/images/client/google.svg';
import LenovoImage from '../../../assets/images/client/lenovo.svg';
import PaypalImage from '../../../assets/images/client/paypal.svg';
import ShopifyImage from '../../../assets/images/client/shopify.svg';
import SpotifyImage from '../../../assets/images/client/spotify.svg';
import LogoIcon from '../../../assets/images/logo-icon-48.png';
import Laptop from '../../../assets/images/bg/laptop.png';

function windowScroll() {
    const navbar = document.getElementById("navbar");
    if (
        document.body.scrollTop >= 50 ||
        document.documentElement.scrollTop >= 50
    ) {
        navbar.classList.add("nav-sticky");
    } else {
        navbar.classList.remove("nav-sticky");
    }
};

onMount(() => {
    window.addEventListener("scroll", windowScroll);
})
</script>

<div>
    <Navbar />
    <section class="bg-half-170 d-table w-100 overflow-hidden bg-soft-primary" id="home">
        <Container>
            <Row class="align-items-center">
                <Col lg={6} md={6}>
                    <div class="title-heading">
                        <img src={LogoIcon} alt="" />
                        <h1 class="heading my-3">Make everything <br /> organize with Motos</h1>
                        <p class="para-desc text-muted">Launch your campaign and benefit from our expertise on designing and managing conversion centered bootstrap v5 html page.</p>
                        <div class="mt-4 pt-2">
                            <a href="/" class="btn btn-primary">Buy Now</a>
                        </div>
                    </div>
                </Col>

                <Col lg={6} md={6} class="mt-4 pt-2 mt-sm-0 pt-sm-0">
                    <div class="img-fluid-responsive position-relative">
                        <img src={Laptop} class="mx-auto d-block" alt="" />
                    </div>
                </Col>
            </Row>
        </Container>
    </section>

    <section class="mt-5 pt-md-5">
        <Container>
            <Row class="justify-content-center">
                <div class="col-lg-2 col-md-2 col-6 text-center py-4 py-sm-0">
                    <img src={AmazonImage} class="avatar avatar-ex-sm" alt="" />
                </div>

                <div class="col-lg-2 col-md-2 col-6 text-center py-4 py-sm-0">
                    <img src={GoogleImage} class="avatar avatar-ex-sm" alt="" />
                </div>

                <div class="col-lg-2 col-md-2 col-6 text-center py-4 py-sm-0">
                    <img src={LenovoImage} class="avatar avatar-ex-sm" alt="" />
                </div>

                <div class="col-lg-2 col-md-2 col-6 text-center py-4 py-sm-0">
                    <img src={PaypalImage} class="avatar avatar-ex-sm" alt="" />
                </div>

                <div class="col-lg-2 col-md-2 col-6 text-center py-4 py-sm-0">
                    <img src={ShopifyImage} class="avatar avatar-ex-sm" alt="" />
                </div>

                <div class="col-lg-2 col-md-2 col-6 text-center py-4 py-sm-0">
                    <img src={SpotifyImage} class="avatar avatar-ex-sm" alt="" />
                </div>
            </Row>
        </Container>
    </section>

    <Feature />

    <Pricing />
    <Review />
    <News />
    <Contact />
    <Footer />
</div>
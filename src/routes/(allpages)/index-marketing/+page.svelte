<script>
    import { Col, Container, Row } from "@sveltestrap/sveltestrap";

    import Navbar from "../../../component/Navbar.svelte";
    import Feature from "../../../component/Feature.svelte";
    import Pricing from "../../../component/Pricing.svelte";
    import Review from "../../../component/Review.svelte";
    import News from "../../../component/News.svelte";
    import Contact from "../../../component/Contact.svelte";
    import Footer from "../../../component/Footer.svelte";

    import BackgroundImage from '../../../assets/images/bg/marketing-shape.png';
    import CelebrationImage from '../../../assets/images/svg/celebration.svg';
    import AmazonImage from '../../../assets/images/client/amazon.svg';
    import GoogleImage from '../../../assets/images/client/google.svg';
    import LenovoImage from '../../../assets/images/client/lenovo.svg';
    import PaypalImage from '../../../assets/images/client/paypal.svg';
    import ShopifyImage from '../../../assets/images/client/shopify.svg';
    import SpotifyImage from '../../../assets/images/client/spotify.svg';

</script>
<div>
    <Navbar />

    <section class="bg-home bg-soft-primary d-flex align-items-center" style="background: url('{BackgroundImage}') center center; height: auto" id="home">
        <Container>
            <Row class="mt-5 pt-5 justify-content-center">
                <div class="col-lg-12 text-center mt-0 mt-md-5 pt-0 pt-md-5">
                    <div class="title-heading">
                        <h4 class="heading my-3">Solve Problem With on Integrated <br /> Marketing Agency</h4>
                        <p class="para-desc mx-auto text-muted">Explore and learn more about everything from machine learning and global payments to  scaling your team.</p>
                    </div>

                    <div class="text-center subcribe-form mt-4 pt-2">
                        <form>
                            <input type="url" id="url" class="border bg-white rounded-lg" style={{ opacity: "0.85" }} required placeholder="https://shreethemes.in" />
                            <button type="submit" class="btn btn-pills btn-primary">Get Started</button>
                        </form>
                    </div>

                    <Row class="justify-content-center">
                        <Col lg={7} md={10}>
                            <div class="home-dashboard">
                                <img src={CelebrationImage} alt="" class="img-fluid" />
                            </div>
                        </Col>
                    </Row>
                </div>
            </Row>
        </Container>
    </section>
    <div class="position-relative">
        <div class="shape marketing-hero overflow-hidden text-light"></div>
    </div>

    <section class="mt-5 pt-md-5">
        <Container>
            <Row class="row justify-content-center">
                <Col lg={2} md={2} class="col-6 text-center py-4 py-sm-0">
                    <img src={AmazonImage} class="avatar avatar-ex-sm" alt="" />
                </Col>

                <Col lg={2} md={2} class="col-6 text-center py-4 py-sm-0">
                    <img src={GoogleImage} class="avatar avatar-ex-sm" alt="" />
                </Col>

                <Col lg={2} md={2} class="col-6 text-center py-4 py-sm-0">
                    <img src={LenovoImage} class="avatar avatar-ex-sm" alt="" />
                </Col>

                <Col lg={2} md={2} class="col-6 text-center py-4 py-sm-0">
                    <img src={PaypalImage} class="avatar avatar-ex-sm" alt="" />
                </Col>

                <Col lg={2} md={2} class="col-6 text-center py-4 py-sm-0">
                    <img src={ShopifyImage} class="avatar avatar-ex-sm" alt="" />
                </Col>

                <Col lg={2} md={2} class="col-6 text-center py-4 py-sm-0">
                    <img src={SpotifyImage} class="avatar avatar-ex-sm" alt="" />
                </Col>
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
<script>
	import { onMount } from 'svelte';
    import {
        Col, Container, Row, Nav,
        NavbarBrand,
        NavbarToggler,
        Collapse,
        NavItem
    } from "@sveltestrap/sveltestrap";
    import { ChevronDownIcon,ArrowUpIcon,AirplayIcon,ApertureIcon,CompassIcon,AwardIcon,PhoneIcon,ThumbsUpIcon,CoffeeIcon,SmileIcon,SettingsIcon,MenuIcon,MessageCircleIcon,CameraIcon,FacebookIcon,InstagramIcon,TwitterIcon,LinkedinIcon } from 'svelte-feather-icons';
    import Counter from './../../../component/counter.svelte';
    import Review from "../../../component/Review.svelte";
    import News from "../../../component/News.svelte";
    import Contact from "../../../component/Contact.svelte";
    import PortfolioSection from "../../../component/Portfolio.svelte";
    import Videomodal from "../../../component/videomodal.svelte";
    import Cta2 from "../../../assets/images/personal/cta-2.jpg";
    import ShreeLogo from "../../../assets/images/brands/shree-logo.png";
    import GoogleLogo from "../../../assets/images/brands/google-logo.png";
    import LenovoLogo from "../../../assets/images/brands/lenovo-logo.png";
    import CircleLogo from "../../../assets/images/brands/circle-logo.png";
    import Logodark from "../../../assets/images/logo-dark.png";
    import Logolight from "../../../assets/images/logo-light.png";
    import About from "../../../assets/images/personal/about.jpg";
    import Hero from "../../../assets/images/personal/hero.png";
    import CTOImage from "../../../assets/images/personal/cta.jpg";
    let scroll = false;
    let isOpenMenu = true;
    onMount(() => {
        if (window.screen.width <= 991){
            isOpenMenu = false;
        }else{
            isOpenMenu = true;
        }
        window.addEventListener("resize", reportWindowSize);
        window.addEventListener("scroll", () => {
            scroll = window.scrollY > 50;
        });
        typewrite();
        window.onscroll = () => {
            const sections = document.querySelectorAll("section");
            const navLi = document.querySelectorAll(".navbar ul.navbar-nav li > a");

             var current = "";

            sections.forEach((section) => {
            const sectionTop = section.offsetTop;
            if (pageYOffset >= sectionTop - 60) {
                current = section.getAttribute("id"); }
            });
            

            navLi.forEach((li) => {
            li.classList.remove("active");
            console.log()
            if (li.classList.contains(current)) {
                console.log('in')
                li.classList.add("active");
            }
            });
        }
    });

    const scrollTop = () =>{
    window.scrollTo({ 
        top: 0,  
        behavior: 'smooth'
        });
    }

        const toggleMenu = () => {
            isOpenMenu = !isOpenMenu;
        }
    class TxtType {
		constructor(el, toRotate, period) {
			this.toRotate = toRotate;
			this.el = el;
			this.loopNum = 0;
			this.period = parseInt(period, 10) || 2000;
			this.txt = '';
			this.tick();
			this.isDeleting = false;
		}
	}

    TxtType.prototype.tick = function () {
        var i = this.loopNum % this.toRotate.length;
        var fullTxt = this.toRotate[i];
        if (this.isDeleting) {
            this.txt = fullTxt.substring(0, this.txt.length - 1);
        } else {
            this.txt = fullTxt.substring(0, this.txt.length + 1);
        }
        this.el.innerHTML = '<span class="wrap">' + this.txt + '</span>';
        var that = this;
        var delta = 200 - Math.random() * 100;
        if (this.isDeleting) { delta /= 2; }
        if (!this.isDeleting && this.txt === fullTxt) {
            delta = this.period;
            this.isDeleting = true;
        } else if (this.isDeleting && this.txt === '') {
            this.isDeleting = false;
            this.loopNum++;
            delta = 500;
        }
        setTimeout(function () {
            that.tick();
        }, delta);
    };

    function typewrite() {
        if (toRotate === 'undefined') {
            changeText()
        }
        else
            var elements = document.getElementsByClassName('typewrite');
        for (var i = 0; i < elements.length; i++) {
            var toRotate = elements[i].getAttribute('data-type');
            var period = elements[i].getAttribute('data-period');
            if (toRotate) {
                new TxtType(elements[i], JSON.parse(toRotate), period);
            }
        }
        // INJECT CSS
        var css = document.createElement("style");
        css.type = "text/css";
        css.innerHTML = ".typewrite > .wrap { border-right: 0.08em solid transparent}";
        document.body.appendChild(css);
    };

    function handleAnchorClick (event) {
		event.preventDefault()
		const link = event.currentTarget
		const anchorId = new URL(link.href).hash.replace('#', '')
		const anchor = document.getElementById(anchorId)
		window.scrollTo({
			top: anchor.offsetTop,
			behavior: 'smooth'
		})
	}
    function reportWindowSize(){
            if (window.screen.width <= 991){
                isOpenMenu = false;
            }else{
                isOpenMenu = true;
            }
        }
</script>
<Counter />
<nav id="navbar" class="navbar navbar-expand-lg fixed-top sticky bg-white">
    <Container>
        <NavbarBrand class="navbar-brand" href="/">
            <img src={Logodark} class="logo-light-mode" alt="" />
            <img src={Logolight} class="logo-dark-mode" alt="" />
        </NavbarBrand>
        <NavbarToggler on:click={toggleMenu}>
            <MenuIcon />
        </NavbarToggler>

        <Collapse isOpen={isOpenMenu} class={`navbar-collapse ${isOpenMenu === true ? 'hidden' : 'show'}`} id="navbarSupportedContent">
            <Nav class="navbar-nav ms-auto mb-2 mb-lg-0" id="navbar-navlist">
                <NavItem>
                    <a spy={true} smooth={true} duration={500} on:click={handleAnchorClick} class="nav-link home active" href="#home">Home</a>
                </NavItem>
                <NavItem>
                    <a spy={true} smooth={true} duration={500} on:click={handleAnchorClick} class="nav-link about" href="#about">About Me</a>
                </NavItem>
                <NavItem>
                    <a spy={true} smooth={true} duration={500} on:click={handleAnchorClick} class="nav-link service" href="#service">Services</a>
                </NavItem>
                <NavItem>
                    <a spy={true} smooth={true} duration={500} on:click={handleAnchorClick} class="nav-link resume" href="#resume">Resume</a>
                </NavItem>
                <NavItem>
                    <a spy={true} smooth={true} duration={500} on:click={handleAnchorClick} class="nav-link portfolio" href="#portfolio">Portfolio</a>
                </NavItem>
                <NavItem>
                    <a spy={true} smooth={true} duration={500} on:click={handleAnchorClick} class="nav-link blog" href="#blog">Blog</a>
                </NavItem>
                <NavItem>
                    <a spy={true} smooth={true} duration={500} on:click={handleAnchorClick} class="nav-link contact" href="#contact">Contact Us</a>
                </NavItem>
            </Nav>

            <ul class="list-inline menu-social mb-0 ps-lg-4 ms-2">
                <li class="list-inline-item">
                    <a href="tel:+15534-468-854" class="text-primary d-flex align-items-center"><span class="btn btn-sm btn-icon btn-pills btn-primary me-2"><PhoneIcon class="icons" /></span> Call Me</a>
                </li>
            </ul>
        </Collapse>
    </Container>
</nav>

<section class="bg-half-170 d-table w-100 bg-light bg-animation-right pb-0 overflow-hidden" id="home">
    <Container>
        <Row class="align-items-center position-relative" style="z-index : 1">
            <Col lg={9} >
                <div class="position-absolute text-mover top-0">
                    <!-- svelte-ignore a11y-distracting-elements -->
                    <marquee>James Davidson</marquee>
                </div>
            </Col>
            <Col lg={7} md={6}>

                <div class="title-heading">
                    <h4 class="display-4 fw-bold">Hello !</h4>
                    <h5 class="heading sub-heading mb-3">I am <span class="typewrite position-relative text-type-element" data-period="2000" data-type='[ "James Davidson", "Photographer", "Web Designer", "UX / UI Designer" ]'></span></h5>
                    <p class="text-muted para-desc mb-0">Obviously I'm a Web Designer. Web Developer with over 3 years of experience. Experienced with all stages of the development cycle for dynamic web projects.</p>

                    <div class="mt-4">
                        <a href="contact" spy={true} smooth={true} duration={500} class="btn btn-primary">Hire Me</a>
                    </div>
                </div>
            </Col>

            <Col lg={5} md={6} class="mt-4 pt-2 mt-sm-0 pt-sm-0">
                <div class="position-relative">
                    <img src={Hero} class="img-fluid" alt="" />

                    <div class="position-absolute top-50 end-0 p-4 d-inline-block bg-white rounded-md shadow-md">
                        <ul class="list-unstyled social-icon social mb-0">
                            <li class="mt-3"><a href={null} class="rounded"><FacebookIcon class="fea icon-sm fea-social" /></a></li>
                            <li class="mt-2"><a href={null} class="rounded"><InstagramIcon class="fea icon-sm fea-social" /></a></li>
                            <li class="mt-2"><a href={null} class="rounded"><TwitterIcon class="fea icon-sm fea-social" /></a></li>
                            <li class="mt-2"><a href={null} class="rounded"><LinkedinIcon class="fea icon-sm fea-social" /></a></li>
                        </ul>

                        <div class="position-absolute top-0 start-50 translate-middle">
                            <a href={null} class="btn btn-pills btn-lg btn-icon btn-primary"><i class="uil uil-share fs-5"></i></a>
                        </div>
                    </div>
                </div>
            </Col>
        </Row>
    </Container>
</section>

<div class="position-relative">
    <div class="text-center position-absolute top-50 start-50 translate-middle z-index-1">
        <div class="play-icon bottom d-inline-block rounded-circle">
            <Videomodal>
                <a href={null} class="play-btn lightbox">
                    <i class="mdi mdi-play rounded-circle"></i>
                </a>
            </Videomodal>
        </div>
    </div>
</div>

<section class="section mt-5" id="about">
    <Container>
        <div class="row align-items-center">
            <div class="col-lg-5 col-md-6">
                <img src={About} class="rounded shadow img-fluid" alt="" />
            </div>

            <div class="col-lg-7 col-md-6 mt-4 mt-sm-0 pt-2 pt-sm-0">
                <div class="ms-lg-5">
                    <div class="section-title">
                        <h4 class="title mb-3">About Me</h4>
                        <p class="text-muted">Obviously I'm a Web Designer. Experienced with all stages of the development cycle for dynamic web projects.</p>
                        <p class="text-muted mb-0">Pursuing this degree will allow me to combine my interest in both technology and business. One day my hope is to become an independent business owner. Regardless of where my career leads me, working remotely remains one of my most important goals. Remote working will allow me to pursue some passions of mine such as online content creation and writing. Thank you for visiting my website!</p>
                    </div>

                    <div class="progress-box mt-4">
                        <h6 class="title fw-normal text-muted">WordPress</h6>
                        <div class="progress">
                            <div class="progress-bar position-relative bg-primary" style="width: 84%">
                                <div class="progress-value d-block text-muted h6">84%</div>
                            </div>
                        </div>
                    </div>
                    <div class="progress-box mt-4">
                        <h6 class="title fw-normal text-muted">Angular / JavaScript</h6>
                        <div class="progress">
                            <div class="progress-bar position-relative bg-primary" style="width: 79%">
                                <div class="progress-value d-block text-muted h6">79%</div>
                            </div>
                        </div>
                    </div>
                    <div class="progress-box mt-4">
                        <h6 class="title fw-normal text-muted">HTML</h6>
                        <div class="progress">
                            <div class="progress-bar position-relative bg-primary" style="width : 95%">
                                <div class="progress-value d-block text-muted h6">95%</div>
                            </div>
                        </div>
                    </div>

                    <div class="mt-4 pt-2">
                        <a spy={true} smooth={true} duration={500} href="portfolio" class="btn btn-soft-primary">View my Projects</a>
                    </div>
                </div>
            </div>
        </div>
    </Container>
</section>

<section class="section bg-light" id="service">
    <Container>
        <div class="row justify-content-center">
            <div class="col-12">
                <div class="section-title text-center mb-4 pb-2">
                    <h4 class="title mb-3">What Do I Offer ?</h4>
                    <p class="para-desc text-muted mx-auto mb-0">Obviously I'm a Web Designer. Experienced with all stages of the development cycle for dynamic web projects.</p>
                </div>
            </div>
        </div>

        <Row>
            <Col lg={4} md={6} class="mt-4 pt-2">
                <div class="card features feature-primary feature-clean feature-transition p-4 py-5 border-0 shadow rounded-md overflow-hidden">
                    <AirplayIcon class="fea icon-lg fea-icon" />
                    <div class="content mt-4">
                        <h5>UX / UI Design</h5>
                        <p class="text-muted mt-3">The phrasal sequence of the Lorem Ipsum text is now so that many DTP programmes can generate</p>

                        <a href={null} class="link">Read more <i class="uil uil-arrow-right"></i></a>
                    </div>
                </div>
            </Col>

            <Col lg={4} md={6} class="mt-4 pt-2">
                <div class="card features feature-primary feature-clean feature-transition p-4 py-5 border-0 shadow rounded-md overflow-hidden">
                    <ApertureIcon class="fea icon-lg fea-icon" />
                    <div class="content mt-4">
                        <h5>Ios App Designer</h5>
                        <p class="text-muted mt-3">The phrasal sequence of the Lorem Ipsum text is now so that many DTP programmes can generate</p>

                        <a href={null} class="link">Read more <i class="uil uil-arrow-right"></i></a>
                    </div>
                </div>
            </Col>

            <Col lg={4} md={6} class="mt-4 pt-2">
                <div class="card features feature-primary feature-clean feature-transition p-4 py-5 border-0 shadow rounded-md overflow-hidden">
                    <CameraIcon class="fea icon-lg fea-icon" />
                    <div class="content mt-4">
                        <h5>Photography</h5>
                        <p class="text-muted mt-3">The phrasal sequence of the Lorem Ipsum text is now so that many DTP programmes can generate</p>

                        <a href={null} class="link">Read more <i class="uil uil-arrow-right"></i></a>
                    </div>
                </div>
            </Col>

            <Col lg={4} md={6} class="mt-4 pt-2">
                <div class="card features feature-primary feature-clean feature-transition p-4 py-5 border-0 shadow rounded-md overflow-hidden">
                    <CompassIcon class="fea icon-lg fea-icon" />
                    <div class="content mt-4">
                        <h5>Graphic Designer</h5>
                        <p class="text-muted mt-3">The phrasal sequence of the Lorem Ipsum text is now so that many DTP programmes can generate</p>

                        <a href={null} class="link">Read more <i class="uil uil-arrow-right"></i></a>
                    </div>
                </div>
            </Col>

            <Col lg={4} md={6} class="mt-4 pt-2">
                <div class="card features feature-primary feature-clean feature-transition p-4 py-5 border-0 shadow rounded-md overflow-hidden">
                    <SettingsIcon class="fea icon-lg fea-icon" />
                    <div class="content mt-4">
                        <h5>Web Security</h5>
                        <p class="text-muted mt-3">The phrasal sequence of the Lorem Ipsum text is now so that many DTP programmes can generate</p>

                        <a href={null} class="link">Read more <i class="uil uil-arrow-right"></i></a>
                    </div>
                </div>
            </Col>

            <Col lg={4} md={6} class="mt-4 pt-2">
                <div class="card features feature-primary feature-clean feature-transition p-4 py-5 border-0 shadow rounded-md overflow-hidden">
                    <MessageCircleIcon class="fea icon-lg fea-icon" />
                    <div class="content mt-4">
                        <h5>24/7 Support</h5>
                        <p class="text-muted mt-3">The phrasal sequence of the Lorem Ipsum text is now so that many DTP programmes can generate</p>

                        <a href={null} class="link">Read more <i class="uil uil-arrow-right"></i></a>
                    </div>
                </div>
            </Col>
        </Row>
    </Container>
</section>

<section class="section" style="background: url('{CTOImage}') top">
    <div class="bg-overlay"></div>
    <Container>
        <Row id="counter">
            <div class="col-lg-3 col-6">
                <div class="counter-box rounded py-3 text-center">
                    <div class="counter-icon">
                        <SmileIcon class="fea icon-md text-primary" />
                    </div>
                    <h3 class="counter-value mt-3 text-white title-dark" data-target="1251">95</h3>
                    <h6 class="counter-head font-weight-normal mb-0 text-white title-dark">Happy Client</h6>
                </div>
            </div>

            <div class="col-lg-3 col-6">
                <div class="counter-box rounded py-3 text-center">
                    <div class="counter-icon">
                        <AwardIcon class="fea icon-md text-primary" />
                    </div>
                    <h3 class="counter-value mt-3 text-white title-dark" data-target="15">1</h3>
                    <h6 class="counter-head font-weight-normal mb-0 text-white title-dark">Award Won</h6>
                </div>
            </div>

            <div class="col-lg-3 col-6">
                <div class="counter-box rounded py-3 text-center">
                    <div class="counter-icon">
                        <CoffeeIcon class="fea icon-md text-primary" />
                    </div>
                    <h3 class="counter-value mt-3 text-white title-dark" data-target="3261">30</h3>
                    <h6 class="counter-head font-weight-normal mb-0 text-white title-dark">Cup of Coffee</h6>
                </div>
            </div>

            <div class="col-lg-3 col-6">
                <div class="counter-box rounded py-3 text-center">
                    <div class="counter-icon">
                        <ThumbsUpIcon class="fea icon-md text-primary" />
                    </div>
                    <h3 class="counter-value mt-3 text-white title-dark" data-target="36">3</h3>
                    <h6 class="counter-head font-weight-normal mb-0 text-white title-dark">Project Complete</h6>
                </div>
            </div>
        </Row>
    </Container>
</section>

<section class="section active" id="resume">
    <Container>
        <Row class="justify-content-center">
            <div class="col-12 text-center">
                <div class="section-title mb-4 pb-2">
                    <div class="position-relative">
                        <h4 class="title mb-4">Work Experience</h4>
                    </div>
                    <p class="text-muted mx-auto para-desc mb-0">Obviously I'm a Web Designer. Experienced with all stages of the development cycle for dynamic web projects.</p>
                </div>
            </div>
        </Row>

        <Row>
            <div class="col-12 mt-4 pt-2">
                <div class="timeline-page position-relative">
                    <div class="timeline-item">
                        <Row>
                            <div class="col-lg-6 col-md-6 col-sm-6">
                                <div class="duration date-label-left position-relative text-md-end">
                                    <img src={ShreeLogo} class="rounded-pill avatar avatar-ex-small" alt="" />
                                    <h5 class="my-2">Self Employed</h5>
                                    <small class="text-muted mb-0">2019-21</small>
                                </div>
                            </div>
                            <div class="col-lg-6 col-md-6 col-sm-6 mt-4 mt-sm-0">
                                <div class="event event-description-right float-left text-start">
                                    <h6 class="title mb-1 text-capitalize">UX / UI Designer</h6>
                                    <p class="timeline-subtitle mt-3 mb-0 text-muted">The generated injected humour, or non-characteristic words etc. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis,</p>
                                </div>
                            </div>
                        </Row>
                    </div>

                    <div class="timeline-item mt-5 pt-4">
                        <Row>
                            <div class="col-lg-6 col-md-6 col-sm-6 order-sm-1 order-2 mt-4 mt-sm-0">
                                <div class="event event-description-left float-left text-end">
                                    <h6 class="title mb-1 text-capitalize">Sr. UX / UI Designer</h6>
                                    <p class="timeline-subtitle mt-3 mb-0 text-muted">The generated injected humour, or non-characteristic words etc. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis,</p>
                                </div>
                            </div>
                            <div class="col-lg-6 col-md-6 col-sm-6 order-sm-2 order-1">
                                <div class="duration duration-right position-relative">
                                    <img src={GoogleLogo} class="rounded-pill avatar avatar-ex-small" alt="" />
                                    <h5 class="my-2">Google Tech.</h5>
                                    <small class="text-muted mb-0">2018-19</small>
                                </div>
                            </div>
                        </Row>
                    </div>

                    <div class="timeline-item mt-5 pt-4">
                        <Row>
                            <div class="col-lg-6 col-md-6 col-sm-6 mt-4 mt-sm-0">
                                <div class="duration date-label-left position-relative text-md-end">
                                    <img src={LenovoLogo} class="rounded-pill avatar avatar-ex-small" alt="" />
                                    <h5 class="my-2">Lenovo Ltd.</h5>
                                    <small class="text-muted mb-0">2016-18</small>
                                </div>
                            </div>
                            <div class="col-lg-6 col-md-6 col-sm-6 mt-4 mt-sm-0">
                                <div class="event event-description-right float-left text-start">
                                    <h6 class="title mb-1 text-capitalize">Jr. UX / UI Designer</h6>
                                    <p class="timeline-subtitle mt-3 mb-0 text-muted">The generated injected humour, or non-characteristic words etc. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis,</p>
                                </div>
                            </div>
                        </Row>
                    </div>

                    <div class="timeline-item mt-5 pt-4">
                        <Row>
                            <div class="col-lg-6 col-md-6 col-sm-6 order-sm-1 order-2 mt-4 mt-sm-0">
                                <div class="event event-description-left float-left text-end">
                                    <h6 class="title mb-1 text-capitalize">Front-end Web Designer</h6>
                                    <p class="timeline-subtitle mt-3 mb-0 text-muted">The generated injected humour, or non-characteristic words etc. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis,</p>
                                </div>
                            </div>
                            <div class="col-lg-6 col-md-6 col-sm-6 order-sm-2 order-1">
                                <div class="duration duration-right position-relative">
                                    <img src={CircleLogo} class="rounded-pill avatar avatar-ex-small" alt="" />
                                    <h5 class="my-2">Circle CI</h5>
                                    <small class="text-muted mb-0">2015-16</small>
                                </div>
                            </div>
                        </Row>
                    </div>
                </div>

            </div>
        </Row>
    </Container>
</section>
<PortfolioSection />
<Review />
<section class="section" style="background: url('{Cta2}') top">
    <div class="bg-overlay"></div>
    <Container>
        <div class="row justify-content-center">
            <div class="col-12 text-center">
                <h4 class="text-light title-dark">I Am Available For Freelancer Projects.</h4>
                <p class="text-white-50 mx-auto mt-4 para-desc">Obviously I'm a Web Designer. Experienced with all stages of the development cycle for dynamic web projects.</p>
                <div class="mt-4">
                    <a href="contact" spy={true} smooth={true} duration={500} class="btn btn-primary mouse-down">Hire me <ChevronDownIcon class="fea icon-sm" /> </a>
                </div>
            </div>
        </div>
    </Container>
</section>
<News />
<Contact />
<footer class="bg-footer footer-bar">
    <div class="footer-py-30">
        <div class="container text-center">
            <div class="row align-items-center justify-content-center">
                <div class="col-sm-8">
                    <div class="text-sm-start">
                        <p class="mb-0">© {(new Date().getFullYear())}{" "} Motos. Design with <i class="mdi mdi-heart text-danger"></i> by <a href={null} class="text-reset">Shreethemes</a>.</p>
                    </div>
                </div>

                <div class="col-sm-4 mt-4 mt-sm-0">
                    <ul class="list-unstyled social-icon text-sm-end foot-social-icon mb-0">
                        <li class="list-inline-item"><a href={null} class="rounded"><i class="uil uil-shopping-cart align-middle" title="Buy Now"></i></a></li>
                        <li class="list-inline-item ms-1"><a href={null} class="rounded"><i class="uil uil-dribbble align-middle" title="dribbble"></i></a></li>
                        <li class="list-inline-item ms-1"><a href={null} class="rounded"><i class="uil uil-behance" title="Behance"></i></a></li>
                        <li class="list-inline-item ms-1"><a href={null} class="rounded"><i class="uil uil-linkedin" title="Linkedin"></i></a></li>
                        <li class="list-inline-item ms-1"><a href={null} class="rounded"><i class="uil uil-facebook-f align-middle" title="facebook"></i></a></li>
                        <li class="list-inline-item ms-1"><a href={null} class="rounded"><i class="uil uil-instagram align-middle" title="instagram"></i></a></li>
                        <li class="list-inline-item ms-1"><a href={null} class="rounded"><i class="uil uil-twitter align-middle" title="twitter"></i></a></li>
                        <li class="list-inline-item ms-1"><a href={null} class="rounded"><i class="uil uil-envelope align-middle" title="email"></i></a></li>
                        <li class="list-inline-item ms-1"><a href={null} class="rounded"><i class="uil uil-file align-middle" title="customization"></i></a></li>
                    </ul>
                </div>
            </div>
        </div>

    </div>
</footer>

<a href="/#" on:click={()=>scrollTop()} id="back-to-top" class={`back-to-top rounded-pill fs-5 ${scroll ? 'd-block' : 'hidden' }`}><ArrowUpIcon class="fea icon-sm icons align-middle" /></a>

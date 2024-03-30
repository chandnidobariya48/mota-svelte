<script>
    import { onMount } from "svelte";
    import {
        Col, Container, Row,
        Nav,
        NavbarBrand,
        NavbarToggler,
        Collapse,
        NavItem,
    } from "@sveltestrap/sveltestrap";
    import {ArrowUpIcon,MenuIcon,VideoIcon } from 'svelte-feather-icons';

    import AgencyFeature from "../../../component/AgencyFeature.svelte";
    import AgencyProject from "../../../component/AgencyProject.svelte";
    import Pricing from "../../../component/Pricing.svelte";
    import AgencyTeam from "../../../component/AgencyTeam.svelte";
    import News from "../../../component/News.svelte";
    import Videomodal from '../../../component/videomodal.svelte'
    import ContactModal from "../../../component/ContactModal.svelte";
    import BackgroundImage1 from "../../../assets/images/bg/5.jpg";
    import AmazonImage from '../../../assets/images/client/amazon.svg';
    import GoogleImage from '../../../assets/images/client/google.svg';
    import LenovoImage from '../../../assets/images/client/lenovo.svg';
    import PaypalImage from '../../../assets/images/client/paypal.svg';
    import ShopifyImage from '../../../assets/images/client/shopify.svg';
    import SpotifyImage from '../../../assets/images/client/spotify.svg';
    import MapImage from '../../../assets/images/map.png';
    import AboutImage from '../../../assets/images/about.jpg';
    import CTAImage from "../../../assets/images/bg/cta.png";
    import Logodark from "../../../assets/images/logo-dark.png";
    import Logolight from "../../../assets/images/logo-light.png";

    let isOpenMenu = true;

    onMount(() => {
        if (window.screen.width <= 991){
            isOpenMenu = false;
        }else{
            isOpenMenu = true;
        }
        window.addEventListener('scroll', windowScroll);
        window.addEventListener('scroll', handleScroll);
        window.addEventListener("resize", reportWindowSize);
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
    })
    let scroll = false;
    const handleScroll = () => {
        if (
            document.body.scrollTop >= 50 ||
            document.documentElement.scrollTop >= 50
        ) {
            scroll = true;
        } else {
            scroll = false;
        }
    };

    const windowScroll = () => {
        const navbar = document.getElementById('navbar');
        if (
            document.body.scrollTop >= 500 ||
            document.documentElement.scrollTop >= 500
        ) {
            navbar.classList.add('nav-sticky');
        } else {
            navbar.classList.remove('nav-sticky');
        }
    };
    
    
    let videoModal = false;

    const openModal = () => {
        videoModal = !videoModal;
    };

    const toggleMenu = () => {
        isMenuOpen = !isMenuOpen;
    }
    let iscontact = false;
    const contactModal = () => {
    iscontact = !iscontact;
  };

  const scrollTop = () =>{
    window.scrollTo({ 
        top: 0,  
        behavior: 'smooth'
        });
    }
    
    
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
<div>
    <nav id="navbar" class="navbar navbar-expand-lg nav-light fixed-top sticky">
        <div class="container">
            <NavbarBrand class="navbar-brand" href="/">
                <span class="logo-light-mode">
                    <img src={Logolight} class="l-light" alt="" />
                    <img src={Logodark} class="l-dark" alt="" />
                </span>
                <img src={Logolight} class="logo-dark-mode" alt="" />
            </NavbarBrand>
            <NavbarToggler on:click={toggleMenu}>
                <MenuIcon />
            </NavbarToggler>

            <Collapse isOpen={isOpenMenu} class={`navbar-collapse ${isOpenMenu === true ? 'hidden' : 'show'}`} id="navbarSupportedContent">
                <Nav class="navbar-nav ms-auto mb-2 mb-lg-0" id="navbar-navlist">
                    <NavItem class="nav-item ms-0">
                        <a href="#home" spy={true} smooth={true} duration={500} on:click={handleAnchorClick} class="nav-link home active">Home</a>
                    </NavItem>
                    <NavItem class="nav-item ms-0">
                        <a href="#feature" spy={true} smooth={true} duration={500} on:click={handleAnchorClick} class="nav-link feature">Features</a>
                    </NavItem>
                    <NavItem class="nav-item ms-0">
                        <a href="#portfolio" spy={true} smooth={true} duration={500} on:click={handleAnchorClick} class="nav-link portfolio">Projects</a>
                    </NavItem>
                    <NavItem class="nav-item ms-0">
                        <a href="#pricing" spy={true} smooth={true} duration={500} on:click={handleAnchorClick} class="nav-link pricing">Pricing</a>
                    </NavItem>
                    <NavItem class="nav-item ms-0">
                        <a href="#team" spy={true} smooth={true} duration={500} on:click={handleAnchorClick} class="nav-link team">Team</a>
                    </NavItem>
                    <NavItem class="nav-item ms-0">
                        <a href="#blog" spy={true} smooth={true} duration={500} on:click={handleAnchorClick} class="nav-link blog">News</a>
                    </NavItem>
                    <NavItem class="nav-item ms-0">
                        <a class="nav-link" on:click={contactModal}>Contact Us</a>
                    </NavItem>
                </Nav>

                <ul class="list-inline menu-social mb-0 ps-lg-4 ms-2">
                    <li class="list-inline-item"><a href="/" class="btn btn-primary">Start Project</a></li>
                </ul>
            </Collapse>

        </div>

    </nav>
    
    <ContactModal iscontact={iscontact} contactModal={contactModal} />

    <section class="bg-home d-flex align-items-center" style="background: url('{BackgroundImage1}')" id="home">
        <div class="bg-overlay bg-linear-gradient-3"></div>
        <Container>
            <Row>
                <Col>
                    <div class="title-heading">
                        <h1 class="heading text-white title-dark mb-4">Bluid your audiance <br /> and sale more</h1>
                        <p class="para-desc text-white-50">Launch your campaign and benefit from our expertise on designing and managing conversion centered bootstrap v5 html page.</p>
                        <div class="mt-4 pt-2">
                            <a href="/" class="btn btn-primary m-1">Get Started</a>
                            <Videomodal>
                                <a data-type="youtube" data-id="yba7hPeTSjk" class="btn btn-icon btn-pills btn-primary m-1 lightbox"><VideoIcon class="icons" /></a><span class="text-uppercase text-white-50 small align-middle ms-2">Watch Now</span>
                            </Videomodal>
                        </div>
                    </div>
                </Col>
            </Row>
        </Container>
    </section>
    <section class="section">
        <Container>
            <div style="background :url('{MapImage}') center center">
                <Row class="align-items-center">
                    <Col lg={6} md={6}>
                        <div class="position-relative me-lg-5">
                            <img src={AboutImage} class="rounded img-fluid mx-auto d-block" alt="" />
                            <div class="play-icon">
                                <Videomodal>
                                    <a on:click={openModal} data-type="youtube" data-id="yba7hPeTSjk" class="play-btn lightbox">
                                        <i class="mdi mdi-play text-primary rounded-circle bg-white shadow"></i>
                                    </a>
                                </Videomodal>
                            </div>
                        </div>
                    </Col>

                    <Col lg={6} md={6} class="mt-4 pt-2 mt-sm-0 pt-sm-0">
                        <div class="section-title">
                            <h4 class="title mb-3">Right Solutions Give You A <br /> Hassle Free Business</h4>
                            <p class="text-muted">This prevents repetitive patterns from impairing the overall visual impression and facilitates the comparison of different typefaces. Furthermore, it is advantageous when the dummy text is relatively realistic so that the layout impression of the final publication is not compromised.</p>
                            <ul class="list-unstyled text-muted">
                                <li class="mb-1"><span class="text-primary h5 me-2"><i class="uil uil-check-circle align-middle"></i></span>Beautiful and easy to understand animations</li>
                                <li class="mb-1"><span class="text-primary h5 me-2"><i class="uil uil-check-circle align-middle"></i></span>Our Talented &amp; Experienced Marketing Agency</li>
                                <li class="mb-1"><span class="text-primary h5 me-2"><i class="uil uil-check-circle align-middle"></i></span>Theme advantages are pixel perfect design</li>
                            </ul>

                            <div class="d-inline-block">
                                <div class="pt-3 d-flex align-items-center border-top">
                                    <i class="uil uil-envelope text-primary me-2 fs-1"></i>
                                    <div class="content">
                                        <p class="mb-0">Need More Help?</p>
                                        <a href="/" class="text-dark h6">Ask us your question</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </Col>
                </Row>
            </div>
        </Container>
    </section>

    <AgencyFeature />

    <AgencyProject />
    <Pricing />

    <section class="section" style="background : url('{CTAImage}') center">
        <div class="bg-overlay"></div>
        <div class="container">
            <div class="row justify-content-center">
                <div class="col">
                    <div class="section-title text-center">
                        <h4 class="title text-white mb-3">Ready to start your next web project now?</h4>
                        <p class="text-white-50 mx-auto para-desc mb-0">Launch your campaign and benefit from our expertise on designing and managing conversion centered bootstrap v5 html page.</p>

                        <div class="mt-4 pt-2">
                            <a href="/" class="btn btn-primary">Get Started !</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <AgencyTeam />

    <News />

    <footer class="bg-footer">
        <div class="container">
            <div class="row">
                <div class="col-12">
                    <div class="py-4">
                        <div class="row justify-content-center">
                            <div class="col-lg-2 col-md-2 col-6 text-center py-4">
                                <img src={AmazonImage} class="avatar avatar-ex-sm" alt="" />
                            </div>

                            <div class="col-lg-2 col-md-2 col-6 text-center py-4">
                                <img src={GoogleImage} class="avatar avatar-ex-sm" alt="" />
                            </div>

                            <div class="col-lg-2 col-md-2 col-6 text-center py-4">
                                <img src={LenovoImage} class="avatar avatar-ex-sm" alt="" />
                            </div>

                            <div class="col-lg-2 col-md-2 col-6 text-center py-4">
                                <img src={PaypalImage} class="avatar avatar-ex-sm" alt="" />
                            </div>

                            <div class="col-lg-2 col-md-2 col-6 text-center py-4">
                                <img src={ShopifyImage} class="avatar avatar-ex-sm" alt="" />
                            </div>

                            <div class="col-lg-2 col-md-2 col-6 text-center py-4">
                                <img src={SpotifyImage} class="avatar avatar-ex-sm" alt="" />
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="footer-py-30 footer-bar">
            <div class="container text-center">
                <div class="row align-items-center justify-content-center">
                    <div class="col-sm-8">
                        <div class="text-sm-start">
                            <p class="mb-0">© {(new Date().getFullYear())}{" "} Motos. Design with <i class="mdi mdi-heart text-danger"></i> by <a href="/" class="text-reset">Shreethemes</a>.</p>
                        </div>
                    </div>

                    <div class="col-sm-4 mt-4 mt-sm-0">
                        <ul class="list-unstyled social-icon text-sm-end foot-social-icon mb-0">
                            <li class="list-inline-item"><a href="/" class="rounded"><i class="uil uil-shopping-cart align-middle" title="Buy Now"></i></a></li>
                            <li class="list-inline-item ms-1"><a href="/" class="rounded"><i class="uil uil-dribbble align-middle" title="dribbble"></i></a></li>
                            <li class="list-inline-item ms-1"><a href="/" class="rounded"><i class="uil uil-behance" title="Behance"></i></a></li>
                            <li class="list-inline-item ms-1"><a href="/" class="rounded"><i class="uil uil-linkedin" title="Linkedin"></i></a></li>
                            <li class="list-inline-item ms-1"><a href="/" class="rounded"><i class="uil uil-facebook-f align-middle" title="facebook"></i></a></li>
                            <li class="list-inline-item ms-1"><a href="/" class="rounded"><i class="uil uil-instagram align-middle" title="instagram"></i></a></li>
                            <li class="list-inline-item ms-1"><a href="/" class="rounded"><i class="uil uil-twitter align-middle" title="twitter"></i></a></li>
                            <li class="list-inline-item ms-1"><a href="/" class="rounded"><i class="uil uil-envelope align-middle" title="email"></i></a></li>
                            <li class="list-inline-item ms-1"><a href="/" class="rounded"><i class="uil uil-file align-middle" title="customization"></i></a></li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </footer>

    <a on:click={scrollTop} id="back-to-top" class={`back-to-top rounded-pill fs-5 ${scroll ? 'd-block' : 'hidden' }`}><ArrowUpIcon class="fea icon-sm icons align-middle" /></a>

</div>
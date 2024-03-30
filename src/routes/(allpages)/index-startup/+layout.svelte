<script>
    import { onMount } from "svelte";
    import {
        Col, Container, Row, Nav, CardBody, Card,
        NavbarBrand,
        NavbarToggler,
        Collapse,
        NavItem
    } from "@sveltestrap/sveltestrap";
    import Counter from "../../../component/counter.svelte";
    import Videomodal from "../../../component/videomodal.svelte";
    import Pricing from "../../../component/Pricing.svelte";
    import News from "../../../component/News.svelte";
    import Contact from "../../../component/Contact.svelte";
    import AgencyProject from "../../../component/AgencyProject.svelte";
    import { ArrowUpIcon,MenuIcon } from 'svelte-feather-icons';
    
    import Laptop from '../../../assets/images/bg/laptop.png';

    import About from '../../../assets/images/about.jpg';
    import CTA from '../../../assets/images/bg/cta.png';
    import Map from '../../../assets/images/map.png';
    import Logo from '../../../assets/images/logo-light.png';
    import Logodark from "../../../assets/images/logo-dark.png";
    import Logolight from "../../../assets/images/logo-light.png";
    
    import Client1 from "../../../assets/images/client/01.jpg";
    import Client2 from "../../../assets/images/client/02.jpg";
    import Client3 from "../../../assets/images/client/03.jpg";
    import Client4 from "../../../assets/images/client/04.jpg";
    
    const team = [
            {
                name: 'Cristino Murphy',
                profile: Client1,
                department: 'Management'
            },
            {
                name: 'Leosy Clony',
                profile: Client2,
                department: 'Management'
            },
            {
                name: 'Amanda Lair',
                profile: Client3,
                department: 'Management'
            },
            {
                name: 'Calvin Carlo',
                profile: Client4,
                department: 'Management'
            }
        ];
        let scroll = false;
        let isOpenMenu = true;
        onMount(() => {
            if (window.screen.width <= 991){
                isOpenMenu = false;
            }else{
                isOpenMenu = true;
            }
            window.addEventListener("scroll", () => {
                scroll = window.scrollY > 50;
            });
            window.addEventListener("scroll", windowScroll);
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
            if (li.classList.contains(current)) {
                li.classList.add("active");
            }
            });
        }
        });

        function reportWindowSize(){
            if (window.screen.width <= 991){
                isOpenMenu = false;
            }else{
                isOpenMenu = true;
            }
        }

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

</script>
<Counter />
<!-- {#if smallDevice}
  <h1>smol</h1>
{:else}
  <h1>big</h1>
{/if} -->
<nav id="navbar" class="navbar navbar-expand-lg nav-light fixed-top sticky">
    <div class="container">
        <NavbarBrand class="navbar-brand" href="/">
            <span class="logo-light-mode">
                <img src={Logodark} class="l-dark" alt="" />
                <img src={Logolight} class="l-light" alt="" />
            </span>
            <img src={Logolight} class="logo-dark-mode" alt="" />
        </NavbarBrand>
        <NavbarToggler on:click={() => (isOpenMenu = !isOpenMenu)}>
            <MenuIcon />
        </NavbarToggler>

        <Collapse isOpen={isOpenMenu} class={`navbar-collapse ${isOpenMenu === true ? 'hidden' : 'show'}`} id="navbarSupportedContent">
            <Nav class="navbar-nav ms-auto mb-2 mb-lg-0" id="navbar-navlist">
                <NavItem>
                    <a href="#home" on:click={handleAnchorClick} spy={true} smooth={true} duration={500} class="nav-link active home">Home</a>
                </NavItem>
                <NavItem>
                    <a href="#service" on:click={handleAnchorClick} spy={true} smooth={true} duration={500} class="nav-link service">Services</a>
                </NavItem>
                <NavItem>
                    <a href="#portfolio" on:click={handleAnchorClick} spy={true} smooth={true} duration={500} class="nav-link portfolio">Portfolio</a>
                </NavItem>
                <NavItem>
                    <a href="#pricing" on:click={handleAnchorClick} spy={true} smooth={true} duration={500} class="nav-link pricing">Pricing</a>
                </NavItem>
                <NavItem>
                    <a href="#team" on:click={handleAnchorClick} spy={true} smooth={true} duration={500} class="nav-link team">Team</a>
                </NavItem>
                <NavItem>
                    <a href="#blog" on:click={handleAnchorClick} spy={true} smooth={true} duration={500} class="nav-link blog">Blog</a>
                </NavItem>
                <NavItem>
                    <a class="nav-link contact" href="#contact" on:click={handleAnchorClick} spy={true} smooth={true} duration={500} >Contact Us</a>
                </NavItem>
            </Nav>

            <ul class="list-inline menu-social mb-0 ps-lg-4 ms-2">
                <li class="list-inline-item"><a href="/auth-login" class="btn btn-primary">Login</a></li>
            </ul>
        </Collapse>

    </div>

</nav>

<slot />

<section class="section bg-light" id="service">
    <Container>
        <div class="row justify-content-center">
            <Col lg={12} >
                <div class="features-absolute rounded shadow px-4 py-5 bg-white">
                    <Row>
                        <div class="col-lg-4 col-md-6">
                            <div class="d-flex features feature-primary">
                                <div class="feature-icon text-center">
                                    <i class="mdi mdi-language-php rounded h4"></i>
                                </div>
                                <div class="flex-1 ms-3">
                                    <h5 class="mt-0">Financial Planning</h5>
                                    <p class="text-muted mb-0">Horem ipsum dolor consectetuer Lorem simply dummy orem commo.</p>
                                </div>
                            </div>
                        </div>

                        <div class="col-lg-4 col-md-6 mt-4 pt-4 mt-sm-0 pt-sm-0">
                            <div class="d-flex features feature-primary">
                                <div class="feature-icon text-center">
                                    <i class="mdi mdi-file-image rounded h4"></i>
                                </div>
                                <div class="flex-1 ms-3">
                                    <h5 class="mt-0">Quality Resourcing</h5>
                                    <p class="text-muted mb-0">When an unknown printer took a galley of type and scrambled it.</p>
                                </div>
                            </div>
                        </div>

                        <div class="col-lg-4 col-md-6 mt-4 pt-4 mt-lg-0 pt-lg-0">
                            <div class="d-flex features feature-primary">
                                <div class="feature-icon text-center">
                                    <i class="uil uil-camera rounded h4"></i>
                                </div>
                                <div class="flex-1 ms-3">
                                    <h5 class="mt-0">Business Services</h5>
                                    <p class="text-muted mb-0">It has survived not only five centuries but leap in typesetting.</p>
                                </div>
                            </div>
                        </div>

                        <div class="col-lg-4 col-md-6 mt-4 pt-4">
                            <div class="d-flex features feature-primary">
                                <div class="feature-icon text-center">
                                    <i class="mdi mdi-google-glass rounded h4"></i>
                                </div>
                                <div class="flex-1 ms-3">
                                    <h5 class="mt-0">Software And Research</h5>
                                    <p class="text-muted mb-0">It was popularised with the release of Letraset sheets sit amet.</p>
                                </div>
                            </div>
                        </div>

                        <div class="col-lg-4 col-md-6 mt-4 pt-4">
                            <div class="d-flex features feature-primary">
                                <div class="feature-icon text-center">
                                    <i class="mdi mdi-source-commit rounded h4"></i>
                                </div>
                                <div class="flex-1 ms-3">
                                    <h5 class="mt-0">Travel And Aviation</h5>
                                    <p class="text-muted mb-0">It is a long established fact that a reader will be distracted.</p>
                                </div>
                            </div>
                        </div>

                        <div class="col-lg-4 col-md-6 mt-4 pt-4">
                            <div class="d-flex features feature-primary">
                                <div class="feature-icon text-center">
                                    <i class="mdi mdi-code-tags rounded h4"></i>
                                </div>
                                <div class="flex-1 ms-3">
                                    <h5 class="mt-0">Healthcare Services</h5>
                                    <p class="text-muted mb-0">A point of using lorem ipsum is that it has normal distribution.</p>
                                </div>
                            </div>
                        </div>
                    </Row>
                </div>
            </Col>
        </div>
    </Container>

    <div class="container mt-100 mt-60">
        <div style="background: url('{Map}') center center">
            <div class="row align-items-center">
                <div class="col-lg-6 col-md-6">
                    <div class="position-relative me-lg-5">
                        <img src={About} class="rounded img-fluid mx-auto d-block" alt="" />
                        <div class="play-icon">
                            <Videomodal>
                                <a href={null} data-type="youtube" data-id="yba7hPeTSjk" class="play-btn lightbox">
                                    <i class="mdi mdi-play text-primary rounded-circle bg-white shadow"></i>
                                </a>
                        </Videomodal>
                        </div>
                    </div>
                </div>

                <div class="col-lg-6 col-md-6 mt-4 pt-2 mt-sm-0 pt-sm-0">
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
                                    <a href={null} class="text-dark h6">Ask us your question</a>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div class="container mt-5">
        <Row>
            <div class="col-md-3 col-6">
                <div class="counter-box position-relative text-center">
                    <h3 class="mb-0 fw-semibold mt-2"><span class="counter-value" data-target="40">3</span>+</h3>
                    <span class="counter-head text-muted">Projects</span>
                </div>
            </div>

            <div class="col-md-3 col-6">
                <div class="counter-box position-relative text-center">
                    <h3 class="mb-0 fw-semibold mt-2"><span class="counter-value" data-target="200">1</span>+</h3>
                    <span class="counter-head text-muted">Clients</span>
                </div>
            </div>

            <div class="col-md-3 col-6">
                <div class="counter-box position-relative text-center">
                    <h3 class="mb-0 fw-semibold mt-2"><span class="counter-value" data-target="457">200</span>K</h3>
                    <span class="counter-head text-muted">Members</span>
                </div>
            </div>

            <div class="col-md-3 col-6">
                <div class="counter-box position-relative text-center">
                    <h3 class="mb-0 fw-semibold mt-2"><span class="counter-value" data-target="150">100</span>+</h3>
                    <span class="counter-head text-muted">Employee</span>
                </div>
            </div>
        </Row>
    </div>
</section>

<section class="section" style="background: url('{CTA}') center">
    <div class="bg-overlay"></div>
    <Container>
        <div class="row justify-content-center">
            <div class="col">
                <div class="section-title text-center">
                    <h4 class="title text-white mb-3">Ready to start your next web project now?</h4>
                    <p class="text-white-50 mx-auto para-desc mb-0">Launch your campaign and benefit from our expertise on designing and managing conversion centered bootstrap v5 html page.</p>

                    <div class="mt-4 pt-2">
                        <a href={null} class="btn btn-primary">Get Started !</a>
                    </div>
                </div>
            </div>
        </div>
    </Container>
</section>

<AgencyProject />
<Pricing />

<section class="section overflow-hidden" id="team">
    <Container>
        <Row class="justify-content-center">
            <div class="col-12">
                <div class="section-title text-center mb-4 pb-2">
                    <h4 class="title mb-3">Our Mind Power</h4>
                    <p class="para-desc mx-auto text-muted mb-0">Launch your campaign and benefit from our expertise on designing and managing conversion centered bootstrap v5 html page.</p>
                </div>
            </div>
        </Row>

        <Row>
            {#each team as item}
                <Col lg={3} md={6} class="mt-4 pt-2">
                    <Card class="border-0 text-center shadow border-0 overflow-hidden rounded">
                        <img src={item.profile} class="img-fluid" alt="" />
                        <CardBody>
                            <h5 class="mb-1">{item.name}</h5>
                            <small class="text-muted">{item.department}</small>
                        </CardBody>
                    </Card>
                </Col>
            {/each}
        </Row>
    </Container>
    <div class="container mt-100 mt-60">
        <div class="row align-items-center">
            <div class="col-md-6">
                <div class="me-lg-5">
                    <div class="row justify-content-center">
                        <div class="col-12">
                            <div class="section-title text-center text-md-start mb-4 pb-2">
                                <h4 class="title mb-3">Work Process</h4>
                                <p class="para-desc text-muted mx-auto mb-0">Launch your campaign and benefit from our expertise on designing and managing conversion centered bootstrap v5 html page.</p>
                            </div>
                        </div>
                    </div>

                    <Row>
                        <div class="col-md-12 mt-4 pt-2">
                            <div class="features feature-primary rounded border-0 d-flex">
                                <div class="feature-icon sm-icon text-center">
                                    <i class="rounded-pill">1</i>
                                </div>

                                <div class="content flex-1 ms-3">
                                    <a href={null} class="title h5 text-dark">Concept</a>
                                    <p class="text-muted mt-2 mb-0">This prevents repetitive impairing the overall facilitates the comparison.</p>
                                </div>
                            </div>
                        </div>

                        <div class="col-md-12 mt-4 pt-2">
                            <div class="features feature-primary rounded border-0 d-flex">
                                <div class="feature-icon sm-icon text-center">
                                    <i class="rounded-pill">2</i>
                                </div>

                                <div class="content flex-1 ms-3">
                                    <a href={null} class="title h5 text-dark">Development</a>
                                    <p class="text-muted mt-2 mb-0">This prevents repetitive impairing the overall facilitates the comparison.</p>
                                </div>
                            </div>
                        </div>

                        <div class="col-md-12 mt-4 pt-2">
                            <div class="features feature-primary rounded border-0 d-flex">
                                <div class="feature-icon sm-icon text-center">
                                    <i class="rounded-pill">3</i>
                                </div>

                                <div class="content flex-1 ms-3">
                                    <a href={null} class="title h5 text-dark">Live Demo</a>
                                    <p class="text-muted mt-2 mb-0">This prevents repetitive impairing the overall facilitates the comparison.</p>
                                </div>
                            </div>
                        </div>
                    </Row>
                </div>
            </div>

            <div class="col-md-6 mt-4 pt-2 mt-sm-0 pt-sm-0">
                <div class="img-fluid-responsive position-relative">
                    <img src={Laptop} class="mx-auto d-block" alt="" />
                </div>
            </div>
        </div>
    </div>
</section>

<News />
<Contact />

<footer class="bg-footer">
    <Container>
        <Row>
            <div class="col-12">
                <div class="footer-py-60">
                    <Row>
                        <div class="col-lg-3 col-12 mb-lg-0 mb-md-4 pb-lg-0 pb-md-2">
                            <a href={null} class="logo-footer">
                                <img src={Logo} height="24" alt="" />
                            </a>
                            <p class="mt-4 mb-0">Start working with Motos that can provide everything you need to generate awareness, drive traffic, connect.</p>

                            <div class="pt-3 d-flex align-items-center">
                                <i class="uil uil-clock text-primary me-2 fs-1"></i>
                                <div class="content">
                                    <p class="mb-1 text-foot">Mon - Sat :</p>
                                    <span class="text-light">10:00 AM To 07:30 PM</span>
                                </div>
                            </div>
                        </div>

                        <div class="col-lg-3 col-md-4 col-12 mt-4 mt-sm-0 pt-2 pt-sm-0">
                            <h5 class="footer-head">Our Services</h5>
                            <ul class="list-unstyled footer-list mt-4">
                                <li><a href={null} class="text-foot"><i class="uil uil-angle-right-b me-1"></i> Financial Planning</a></li>
                                <li><a href={null} class="text-foot"><i class="uil uil-angle-right-b me-1"></i> Software and Research</a></li>
                                <li><a href={null} class="text-foot"><i class="uil uil-angle-right-b me-1"></i> Business Services</a></li>
                                <li><a href={null} class="text-foot"><i class="uil uil-angle-right-b me-1"></i> Quality Resourcing</a></li>
                                <li><a href={null} class="text-foot"><i class="uil uil-angle-right-b me-1"></i> Travel and Aviation</a></li>
                            </ul>
                        </div>

                        <div class="col-lg-3 col-md-4 col-12 mt-4 mt-sm-0 pt-2 pt-sm-0">
                            <h5 class="footer-head">Get In Touch</h5>

                            <p class="mt-4">C/54 Northwest Freeway, Suite <br />558, Houston, USA 485</p>
                            <ul class="list-unstyled footer-list mt-3">
                                <li>Phone: <a href="tel:+152534-468-854" class="text-light">+152 534-468-854</a></li>
                                <li>Email: <a href="mailto:contact@example.com" class="text-light">contact@example.com</a></li>
                            </ul>
                        </div>

                        <div class="col-lg-3 col-md-4 col-12 mt-4 mt-sm-0 pt-2 pt-sm-0">
                            <h5 class="footer-head">Newsletter</h5>
                            <p class="mt-4">Sign up and receive the latest tips via email.</p>
                            <form>
                                <Row>
                                    <Col lg={12} >
                                        <div class="foot-subscribe mb-3">
                                            <label for="emailsubscribe" class="form-label">Write your email <span class="text-danger">*</span></label>
                                            <input type="email" name="email" id="emailsubscribe" class="form-control rounded" placeholder="Your email : " required />
                                        </div>
                                    </Col>
                                    <Col lg={12} >
                                        <div class="d-grid">
                                            <input type="submit" id="submitsubscribe" name="send" class="btn btn-soft-primary" value="Subscribe" />
                                        </div>
                                    </Col>
                                </Row>
                            </form>
                        </div>
                    </Row>
                </div>
            </div>
        </Row>
    </Container>

    <div class="footer-py-30 footer-bar">
        <div class="container text-center">
            <Row class="align-items-center justify-content-center">
                <Col sm={8}>
                    <div class="text-sm-start">
                        <p class="mb-0">© {(new Date().getFullYear())}{" "} Motos. Design with <i class="mdi mdi-heart text-danger"></i> by <a href={null} class="text-reset">Shreethemes</a>.</p>
                    </div>
                </Col>

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
            </Row>
        </div>
    </div>
</footer>
<a href="/#" on:click={()=>scrollTop()} id="back-to-top" class={`back-to-top rounded-pill fs-5 ${scroll ? 'd-block' : 'hidden' }`}><ArrowUpIcon class="fea icon-sm icons align-middle" /></a>
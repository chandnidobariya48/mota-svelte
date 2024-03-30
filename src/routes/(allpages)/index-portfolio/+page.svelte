<script>
    import { onMount } from "svelte";
    import {
        Col, Container, Row, Modal, ModalHeader, ModalBody, Nav,
        NavbarBrand,
        NavbarToggler,
        Collapse,
        NavItem
    } from "@sveltestrap/sveltestrap";
    import {
    LightboxGallery,
    GalleryThumbnail,
    GalleryImage,
  } from "svelte-lightbox";
    import {CameraIcon ,FacebookIcon,InstagramIcon,LinkedinIcon,MenuIcon} from 'svelte-feather-icons';
    import ContactModal from "../../../component/ContactModal.svelte";
    import Videomodal from "../../../component/videomodal.svelte";
    import Image1 from "../../../assets/images/portfolio/11.jpg";
    import Image2 from "../../../assets/images/portfolio/12.jpg";
    import Image3 from "../../../assets/images/portfolio/13.jpg";
    import Image4 from "../../../assets/images/portfolio/14.jpg";
    import Image5 from "../../../assets/images/portfolio/15.jpg";
    import Image6 from "../../../assets/images/portfolio/16.jpg";
    import Logo from "../../../assets/images/logo-icon-64.png";
    import Logodark from "../../../assets/images/logo-dark.png";
    import Logolight from "../../../assets/images/logo-light.png";
    let isOpenMenu = true;
    const portfolioList = [
            {
    
                image: Image1,
                title: 'Iphone mockup',
                subtext: 'Branding'
            },
            {
                image: Image2,
                title: 'Iphone mockup',
                subtext: 'Designing'
            }, {
                image: Image3,
                title: 'Iphone mockup',
                subtext: 'Branding'
            }, {
                image: Image4,
                title: 'Iphone mockup',
                subtext: 'Photography'
            }, {
                image: Image5,
                title: 'Iphone mockup',
                subtext: 'Development'
            }, {
                image: Image6,
                title: 'Iphone mockup',
                subtext: 'Development'
            }
        ];
    
        const handleScroll = () => {
            const navbar = document.getElementById('navbar');
    
            if (
                document.body.scrollTop >= 50 ||
                document.documentElement.scrollTop >= 50
            ) {
                navbar.classList.add("nav-sticky");
            } else {
                navbar.classList.remove("nav-sticky");
            }
        };
    
        const toggleMenu = () => {
            isOpenMenu = !isOpenMenu;
        }
    
        let filterPortfolio = null;
        let filterData = filterPortfolio ? portfolioList.filter((item) => item.subtext === filterPortfolio) : portfolioList;
        const matchsubtext = (subtext) => {
            filterPortfolio = subtext;
            filterData = filterPortfolio && subtext != 'All' ? portfolioList.filter((item) => item.subtext === filterPortfolio) : portfolioList;
        };
    
        onMount(() => {
            if (window.screen.width <= 991){
                isOpenMenu = false;
            }else{
                isOpenMenu = true;
            }
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
        });

        let iscontact = false;
            const contactModal = () => {
            iscontact = !iscontact;
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
<div>
    <nav id="navbar" class="navbar navbar-expand-lg fixed-top sticky">
        <div class="container">
            <NavbarBrand class="navbar-brand" href="/">
                <img src={Logodark} class="logo-light-mode" alt="" />
                <img src={Logolight} class="logo-dark-mode" alt="" />
            </NavbarBrand>
            <NavbarToggler on:click={toggleMenu}>
                <MenuIcon />
            </NavbarToggler>

            <Collapse isOpen={isOpenMenu} class={`navbar-collapse ${isOpenMenu === true ? 'hidden' : 'show'}`} id="navbarSupportedContent">
                <Nav class="navbar-nav mx-auto mb-2 mb-lg-0" id="navbar-navlist">
                    <NavItem>
                        <a spy={true} smooth={true} duration={500} on:click={handleAnchorClick} class="nav-link home active" href="#home">Home</a>
                    </NavItem>
                    <NavItem>
                        <a spy={true} smooth={true} duration={500} on:click={handleAnchorClick} class="nav-link portfolio" href="#portfolio">Works</a>
                    </NavItem>
                    <NavItem>
                        <a class="nav-link" on:click={contactModal}>Contact Us</a>
                    </NavItem>
                </Nav>

                <ul class="list-inline menu-social mb-0 ps-lg-4 ms-2">
                    <li class="list-inline-item"><a href={null} class="btn btn-sm btn-icon btn-pills btn-primary"><FacebookIcon size="24" class="icons" /></a></li>
                    <li class="list-inline-item ms-1"><a href={null} class="btn btn-sm btn-icon btn-pills btn-primary"><InstagramIcon size="24" class="icons" /></a></li>
                    <li class="list-inline-item ms-1"><a href={null} class="btn btn-sm btn-icon btn-pills btn-primary"><LinkedinIcon size="24" class="icons" /></a></li>
                </ul>
            </Collapse>

        </div>
    </nav>

    <section class="bg-half d-table w-100" id="home">
        <div class="background-lines">
            <div class="line"></div>
            <div class="line"></div>
            <div class="line"></div>
        </div>
        <Container>
            <Row class="mt-5 justify-content-center">
                <Col md={9} class="mb-5">
                    <div class="title-heading text-center">
                        <h5 class="text-muted fw-normal">Minimalist Portfolio Creator</h5>
                        <h4 class="heading text-shadow-title fw-bold mb-4">We Built Creative & Classic Portfolio</h4>
                        <p class="text-muted para-desc mx-auto">Motos is a Creative Agency & Startup Studio that provides Digital Products and Services turns to focus on client success.</p>
                        <div class="mt-4 play-icon bottom d-inline-block rounded-circle">
                            <Videomodal>
                                <a href={null} class="play-btn lightbox">
                                    <i class="mdi mdi-play rounded-circle"></i>
                                </a>
                            </Videomodal>
                        </div>
                    </div>
                </Col>
            </Row>
        </Container>

        <section class="container mt-100 mt-60" id="portfolio">
            <Row class="justify-content-center">
                <div class="col-12 filters-group-wrap text-center">
                    <div class="filters-group">
                    <ul class="container-filter mb-4 categories-filter list-unstyled filter-options">
                    
                    <li class={`${filterPortfolio === 'All' ? 'active' : ''} list-inline-item categories h6 position-relative text-dark active`} data-group="all" on:click={ () => matchsubtext('All')}>All</li>
                    <li class={`${filterPortfolio === 'Branding' ? 'active' : ''}  list-inline-item categories h6 position-relative text-dark`} data-group="branding" on:click={ () => matchsubtext('Branding')}>Branding</li>
                    <li class={`${filterPortfolio === 'Designing' ? 'active' : ''} list-inline-item categories h6 position-relative text-dark`} data-group="designing" on:click={ () => matchsubtext('Designing')}>Designing</li>
                    <li class={`${filterPortfolio === 'Photography' ? 'active' : ''} list-inline-item categories h6 position-relative text-dark`} data-group="photography" on:click={ () => matchsubtext('Photography')}>Photography</li>
                    <li class={`${filterPortfolio === 'Development' ? 'active' : ''} list-inline-item categories h6 position-relative text-dark`} data-group="development" on:click={ () => matchsubtext('Development')}>Development</li>
                </ul>
                    </div>
                </div>
            </Row>

            <Row id="grid" class=" g-4">
                {#each filterData as item,index}
                <LightboxGallery activeImage={index}>
                    <svelte:fragment slot="thumbnail">
                    <div class="col-lg-4 col-md-6 col-12 picture-item">
                        <div class="card border-0 project project-primary position-relative d-block overflow-hidden rounded">
                            <div class="card-body p-0">
                                <img src={item.image} class="img-fluid" alt="workimage" />
                                <div class="overlay-work bg-dark"></div>
                                <div class="content bg-white p-3 rounded shadow start-0 end-0 bottom-0 m-3">
                                    <a href={null} class="text-dark title h5">{item.title}</a>
                                    <h6 class="text-muted fw-normal mt-2 tag mb-0">{item.subtext}</h6>
                                </div>
                                <div class="icons text-center">
                                    <GalleryThumbnail><a href={null} class="btn btn-icon btn-pills lightbox"><CameraIcon class="fea icon-sm image-icon" /></a>
                                    </GalleryThumbnail>
                                </div>
                            </div>
                        </div>
                    </div>
                </svelte:fragment>
                {#each filterData as item, index}
                <GalleryImage>
                    <img src={item.image} alt="Simple lightbox-{index}" />
                </GalleryImage>
                {/each}
                </LightboxGallery>
                {/each}
            </Row>
            <Row class="text-center">
                <div class="col-12 mt-4 pt-2">
                    <a href={null} class="btn btn-pills btn-primary">See works</a>
                </div>
            </Row>
        </section>

        <Container class="mt-100 mt-60">
            <Row class="justify-content-center">
                <div class="col-12">
                    <div class="section-title text-center">
                        <h5 class="text-muted fw-normal">Available for freelance projects</h5>
                        <h1 class="fw-bold display-6 my-4">Do you have designing project? <br /> Let's talk.</h1>
                        <div class="mt-4 pt-2">
                            <a href={null} data-bs-toggle="modal" on:click={() => contactModal(true)} class="btn btn-pills btn-primary">Contact us</a>
                        </div>
                    </div>
                </div>
            </Row>
        </Container>
    </section>

    <ContactModal iscontact={iscontact} contactModal={contactModal} />

    <footer class="footer bg-footer">
        <div class="footer-py-60">
            <Container>
                <div class="row justify-content-center">
                    <div class="col-12 text-center">
                        <a href={null}><img src={Logo} alt="" /></a>
                        <p class="para-desc mx-auto copy-rights mt-5">Motos is a high-quality creative minimal portfolio template with great style, modern, creative, clean code and responsive design.</p>
                        <ul class="list-unstyled social-icon foot-social-icon mt-5 mb-0">
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
            </Container>
        </div>

        <div class="footer-py-30 footer-bar">
            <Container class="text-center">
                <div class="row align-items-center">
                    <div class="col">
                        <p class="mb-0">© {(new Date().getFullYear())}{" "} Motos. Design with <i class="mdi mdi-heart text-danger"></i> by <a href={null} class="text-reset">Shreethemes</a>.</p>
                    </div>
                </div>
            </Container>
        </div>
    </footer>
</div>
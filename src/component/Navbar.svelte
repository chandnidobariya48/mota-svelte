<script>
import { onMount } from 'svelte';
import {
    NavbarBrand,
    NavbarToggler,
    NavItem,
    Nav,
    Collapse
} from '@sveltestrap/sveltestrap';
// Import Logo
import {MenuIcon} from 'svelte-feather-icons';
import logodark from "../assets/images/logo-dark.png";
import logolight from "../assets/images/logo-light.png";
let isOpenMenu = true;
onMount(() => {
    if (window.screen.width <= 991){
        isOpenMenu = false;
    }else{
        isOpenMenu = true;
    }
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
        console.log()
        if (li.classList.contains(current)) {
            console.log('in')
            li.classList.add("active");
        }
        });
    }
});

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


<nav id="navbar" class="navbar navbar-expand-lg fixed-top sticky">
    <div class="container">
        <NavbarBrand class="navbar-brand" href="/">
            <img src={logodark} class="logo-light-mode" alt="" />
            <img src={logolight} class="logo-dark-mode" alt="" />
        </NavbarBrand>
        <NavbarToggler class="navbar-toggler" on:click={() => (isOpenMenu = !isOpenMenu)}>
            <MenuIcon />
        </NavbarToggler>

        <Collapse isOpen={isOpenMenu} class={`navbar-collapse ${isOpenMenu === true ? 'hidden' : 'show'}`} id="navbarSupportedContent">

            <Nav class="navbar-nav ms-auto mb-2 mb-lg-0" id="navbar-navlist">
                <NavItem>
                    <a spy={true} smooth={true} duration={500} href="#home" on:click={handleAnchorClick} class="nav-link active home">Home</a>
                </NavItem>
                <NavItem>
                    <a spy={true} smooth={true} duration={500} href="#features" on:click={handleAnchorClick} class="nav-link features">Features</a>
                </NavItem>
                <NavItem>
                    <a spy={true} smooth={true} duration={500} href="#pricing" on:click={handleAnchorClick} class="nav-link pricing">Pricing</a>
                </NavItem>
                <NavItem>
                    <a spy={true} smooth={true} duration={500} href="#review" on:click={handleAnchorClick} class="nav-link review">Review</a>
                </NavItem>
                <NavItem>
                    <a spy={true} smooth={true} duration={500} href="#blog" on:click={handleAnchorClick} class="nav-link blog">News</a>
                </NavItem>
                <NavItem>
                    <a spy={true} smooth={true} duration={500} href="#contact" on:click={handleAnchorClick} class="nav-link contact">Contact Us</a>
                </NavItem>
            </Nav>

            <ul class="list-inline menu-social mb-0 ps-lg-4 ms-2">
                <li class="list-inline-item"><a href="/auth-login" class="text-dark fw-semibold text-uppercase small">Login</a></li>
                <li class="list-inline-item ms-2"><a href="/auth-signup" class="btn btn-primary text-uppercase">Sign Up</a></li>
            </ul>
        </Collapse>
    </div>
</nav>
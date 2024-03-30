<script>
import { Col, Container, Row } from '@sveltestrap/sveltestrap';
import {
    LightboxGallery,
    GalleryThumbnail,
    GalleryImage,
  } from "svelte-lightbox";
import Image1 from "../assets/images/portfolio/11.jpg";
import Image2 from "../assets/images/portfolio/12.jpg";
import Image3 from "../assets/images/portfolio/13.jpg";
import Image4 from "../assets/images/portfolio/14.jpg";
import Image5 from "../assets/images/portfolio/15.jpg";
import Image6 from "../assets/images/portfolio/16.jpg";
import Image7 from "../assets/images/portfolio/17.jpg";
import Image8 from "../assets/images/portfolio/18.jpg";
import {CameraIcon } from 'svelte-feather-icons';

const data = [
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
        },
        {
            image: Image7,
            title: 'Iphone mockup',
            subtext: 'Branding'
        },
        {
            image: Image8,
            title: 'Iphone mockup',
            subtext: 'Development'
        }
    ];

    let filterPortfolio = null;

    let filterData = filterPortfolio ? data.filter((item) => item.subtext === filterPortfolio) : data;

    const matchsubtext = (subtext) => {
        filterPortfolio = subtext;
        filterData = filterPortfolio && subtext != 'All' ? data.filter((item) => item.subtext === filterPortfolio) : data;
    };

</script>


<section class="section bg-light" id="portfolio">
    <Container>
        <div class="row justify-content-center">
            <div class="col-12 text-center">
                <div class="section-title mb-4 pb-2">
                    <div class="position-relative">
                        <h4 class="title mb-4">Portfolio &amp; Projects</h4>
                    </div>
                    <p class="text-muted mx-auto para-desc mb-0">Obviously I'm a Web Designer. Experienced with all stages of the development cycle for dynamic web projects.</p>
                </div>
            </div>
        </div>
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
                <Col lg={3} md={4} class="col-12 picture-item">
                    <div class="card border-0 project project-primary position-relative d-block overflow-hidden rounded">
                        <div class="card-body p-0">
                            <img src={item.image} class="img-fluid" alt="workimage" />
                            <div class="overlay-work bg-dark"></div>
                            <div class="content bg-white p-3 rounded shadow start-0 end-0 bottom-0 m-3">
                                <a href="/" class="text-dark title h5">{item.title}</a>
                                <h6 class="text-muted fw-normal mt-2 tag mb-0">{item.subtext}</h6>
                            </div>
                            <div class="icons text-center">
                                <GalleryThumbnail><a href={null} class="btn btn-icon btn-pills lightbox"><CameraIcon class="fea icon-sm image-icon" /></a></GalleryThumbnail>
                            </div>
                        </div>
                    </div>
                </Col>
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
                <a href="/" class="btn btn-pills btn-primary">See works</a>
            </div>
        </Row>
    </Container>
</section>
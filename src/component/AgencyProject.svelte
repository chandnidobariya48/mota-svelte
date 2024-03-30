<script>
import { Col, Row, Card, CardBody, Container } from '@sveltestrap/sveltestrap';
import {
    LightboxGallery,
    GalleryThumbnail,
    GalleryImage,
  } from "svelte-lightbox";

import Image1 from "../assets/images/portfolio/1.jpg";
import Image2 from "../assets/images/portfolio/2.jpg";
import Image3 from "../assets/images/portfolio/3.jpg";
import Image4 from "../assets/images/portfolio/4.jpg";
import Image5 from "../assets/images/portfolio/5.jpg";
import Image6 from "../assets/images/portfolio/6.jpg";
import Image7 from "../assets/images/portfolio/7.jpg";
import Image8 from "../assets/images/portfolio/8.jpg";
import {CameraIcon } from 'svelte-feather-icons';

    /**
     * Agency project section
     */

    const projectList = [
        {

            image: Image1,
            title: 'Mockup Collection',
            subtext: 'Branding'
        },
        {
            image: Image2,
            title: 'Mockup Collection',
            subtext: 'Designing'
        }, {
            image: Image3,
            title: 'Abstract images',
            subtext: 'Abstract'
        }, {
            image: Image4,
            title: 'Yellow bg with Books',
            subtext: 'Books'
        }, {
            image: Image5,
            title: 'Company V-card',
            subtext: 'V-card'
        }, {
            image: Image6,
            title: 'Mockup box with paints',
            subtext: 'Photography'
        },
        {
            image: Image7,
            title: 'Coffee cup',
            subtext: 'Cups'
        },
        {
            image: Image8,
            title: 'Pen and article',
            subtext: 'Article'
        }
    ];

</script>

<section class="section" id="portfolio">
    <Container>
        <Row class="justify-content-center">
            <Col>
                <div class="section-title text-center mb-4 pb-2">
                    <h4 class="title mb-3">Our Works & Projects</h4>
                    <p class="text-muted mx-auto para-desc mb-0">Launch your campaign and benefit from our expertise on designing and managing conversion centered bootstrap v5 html page.</p>
                </div>
            </Col>
        </Row>

        <Row>
            {#each projectList as item,index}
            <LightboxGallery activeImage={index}>
                <svelte:fragment slot="thumbnail">
                    <Col lg={3} md={6} class="col-12 mt-4 pt-2">
                        <Card class="border-0 project project-primary position-relative d-block overflow-hidden rounded">
                            <CardBody class="p-0">
                                <img src={item.image} class="img-fluid" alt="workimage" />
                                <div class="overlay-work bg-dark"></div>
                                <div class="content">
                                    <h6 class="mb-0"><a href="/" class="text-white title">{item.title}</a></h6>
                                    <p class="text-light tag mb-0">{item.subtext}</p>
                                </div>
                                <div class="icons text-center">
                                    <GalleryThumbnail>
                                    <a href={null} class="btn btn-icon btn-pills lightbox">
                                        <CameraIcon class="fea icon-sm image-icon" /></a>
                                    </GalleryThumbnail>
                                </div>
                            </CardBody>
                        </Card>
                    </Col>
                </svelte:fragment>
                {#each projectList as item, index}
                <GalleryImage>
                    <img src={item.image} alt="Simple lightbox-{index}" />
                </GalleryImage>
                {/each}
            </LightboxGallery>
            {/each}
        </Row>
    </Container>
</section>
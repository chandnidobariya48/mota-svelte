<script>
    import { Col, Row } from '@sveltestrap/sveltestrap';

    import BackgroudImage from "../assets/images/bg/6.jpg";

    const AgencyFeature = [
        {
            id: '1',
            icon: 'mdi mdi-language-php',
            title: "Financial Planning",
            description: "Horem ipsum dolor consectetuer Lorem simply dummy orem commo."
        },
        {
            id: '2',
            icon: 'mdi mdi-file-image',
            title: "Quality Resourcing",
            description: 'When an unknown printer took a galley of type and scrambled it.'
        },
        {
            id: '3',
            icon: 'uil uil-camera',
            title: "Business Services",
            description: 'It has survived not only five centuries but leap in typesetting.'
        },
        {
            id: '4',
            icon: 'mdi mdi-google-glass',
            title: "Software And Research",
            description: 'It was popularised with the release of Letraset sheets sit amet.'
        }, {
            id: '5',
            icon: 'mdi mdi-source-commit',
            title: "Travel And Aviation",
            description: 'It is a long established fact that a reader will be distracted.'
        }, {
            id: '6',
            icon: 'mdi mdi-code-tags',
            title: "Healthcare Services",
            description: 'A point of using lorem ipsum is that it has normal distribution.'
        },
    ];

</script>

<section style="background : url('{BackgroudImage}') top" id="feature">
    <div class="container-fluid px-0">
        <Row class="g-0">
            <Col lg={6} class="order-1 order-lg-2 py-5 py-lg-0">
                <div class="py-5 py-lg-0 my-5 my-lg-0"></div>
            </Col>

            <Col lg={6} class="order-2 order-lg-1">
                <div class="bg-light px-4 py-5 px-md-5">
                    <div class="row">
                        <div class="col">
                            <div class="section-title mb-4 pb-2">
                                <h4 class="title mb-3">Our Features</h4>
                                <p class="text-muted para-desc mb-0">Launch your campaign and benefit from our expertise on designing and managing conversion centered bootstrap v5 html page.</p>
                            </div>
                        </div>
                    </div>

                    <Row>
                        {#each AgencyFeature as item}
                        <Col md={6} class="mt-4 pt-2">
                            <div class="features feature-primary">
                                <div class="feature-icon text-center">
                                    <i class={item.icon + " rounded h4"}></i>
                                </div>
                                <div class="flex-1 mt-4">
                                    <h5 class="mt-0">{item.title}</h5>
                                    <p class="text-muted mb-0">{item.description}</p>
                                </div>
                            </div>
                        </Col>
                        {/each}
                    </Row>
                </div>
            </Col>
        </Row>
    </div>
</section>
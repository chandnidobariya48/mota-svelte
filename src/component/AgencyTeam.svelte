<script>
import { Container, CardBody, Col, Row, Card } from '@sveltestrap/sveltestrap';

import Image1 from "../assets/images/client/01.jpg";
import Image2 from "../assets/images/client/02.jpg";
import Image3 from "../assets/images/client/03.jpg";
import Image4 from "../assets/images/client/04.jpg";

/**
 * Agency team section
 */
    const team =
        [
            {
                name: 'Cristino Murphy',
                profile: Image1,
                department: 'Management'
            },
            {
                name: 'Leosy Clony',
                profile: Image2,
                department: 'Management'
            },
            {
                name: 'Amanda Lair',
                profile: Image3,
                department: 'Management'
            },
            {
                name: 'Calvin Carlo',
                profile: Image4,
                department: 'Management'
            }
        ];
</script>
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
</section>
<script>
import { Col, Row, Card, CardBody } from "@sveltestrap/sveltestrap";
import {ArrowLeftIcon } from 'svelte-feather-icons';

import BackgroundImage from '../../../assets/images/bg/1.jpg';
import Logo from '../../../assets/images/logo-icon-64.png';
</script>

<div class="back-to-home">
    <a href={null} class="back-button btn btn-icon btn-primary"><ArrowLeftIcon class="icons" /></a>
</div>

<section class="cover-user bg-white">
    <div class="container-fluid px-0">
        <Row class="g-0 position-relative">
            <Col lg={4} class="cover-my-30 order-2">
                <div class="cover-user-img d-flex align-items-center">
                    <Row>
                        <div class="col-12">
                            <div class="d-flex flex-column auth-hero">
                                <div class="mt-md-5 text-center">
                                    <a href={null}><img src={Logo} alt="" /></a>
                                </div>
                                <div class="title-heading my-lg-auto">
                                    <Card class="border-0" style="z-index : 1">
                                        <CardBody class="p-0">
                                            <h4 class="card-title">Signup</h4>
                                            <form class="login-form mt-4">
                                                <Row>
                                                    <Col md={6} >
                                                        <div class="mb-3">
                                                            <label for="" class="form-label">First name <span class="text-danger">*</span></label>
                                                            <input type="text" class="form-control" placeholder="First Name" name="s" required />
                                                        </div>
                                                    </Col>

                                                    <Col md={6} >
                                                        <div class="mb-3">
                                                            <label for="" class="form-label">Last name <span class="text-danger">*</span></label>
                                                            <input type="text" class="form-control" placeholder="Last Name" name="s" required />
                                                        </div>
                                                    </Col>

                                                    <Col md={12} >
                                                        <div class="mb-3">
                                                            <label for="" class="form-label">Your Email <span class="text-danger">*</span></label>
                                                            <input type="email" class="form-control" placeholder="Email" name="email" required />
                                                        </div>
                                                    </Col>
                                                    <Col md={12}>
                                                        <div class="mb-3">
                                                            <label for="" class="form-label">Password <span class="text-danger">*</span></label>
                                                            <input type="password" class="form-control" placeholder="Password" required />
                                                        </div>
                                                    </Col>

                                                    <Col md={12}>
                                                        <div class="mb-3">
                                                            <div class="form-check">
                                                                <input class="form-check-input" type="checkbox" value="" id="flexCheckDefault" />
                                                                <label for="" class="form-check-label" >I Accept <a href={null} class="text-primary">Terms And Condition</a></label>
                                                            </div>
                                                        </div>
                                                    </Col>
                                                    <div class="col-lg-12 mb-0">
                                                        <div class="d-grid">
                                                            <button class="btn btn-primary">Register</button>
                                                        </div>
                                                    </div>

                                                    <div class="mx-auto">
                                                        <p class="mb-0 mt-3"><small class="text-dark me-2">Already have an account ?</small> <a href="/auth-login" class="text-dark fw-bold">Sign in</a></p>
                                                    </div>
                                                </Row>
                                            </form>
                                        </CardBody>
                                    </Card>
                                </div>
                                <div class="mb-md-5 text-center">
                                    <p class="mb-0 text-muted">© {(new Date().getFullYear())}{" "} Motos. Design with <i class="mdi mdi-heart text-danger"></i> by <a href={null} class="text-reset">Shreethemes</a>.</p>
                                </div>
                            </div>
                        </div>
                    </Row>
                </div>
            </Col>

            <div class="col-lg-8 offset-lg-4 padding-less img order-1" style="background-image : url('{BackgroundImage}')"></div>
        </Row>
    </div>
</section>
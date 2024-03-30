<script>
    import {
         Modal, ModalHeader, ModalBody
    } from "@sveltestrap/sveltestrap";
    export let iscontact,contactModal;
</script>
<Modal isOpen={iscontact} toggle={contactModal}>
    <ModalHeader >
        Contact Us
    </ModalHeader>
    <ModalBody>
        <form method="post" name="myForm">
            <p id="error-msg" class="mb-0"></p>
            <div id="simple-msg"></div>
            <div class="row">
                <div class="col-md-6">
                    <div class="mb-3">
                        <label for="" class="form-label fw-normal">Your Name <span class="text-danger">*</span></label>
                        <input name="name" id="name" type="text" class="form-control" placeholder="Name :" />
                    </div>
                </div>

                <div class="col-md-6">
                    <div class="mb-3">
                        <label for="" class="form-label fw-normal">Your Email <span class="text-danger">*</span></label>
                        <input name="email" id="email" type="email" class="form-control" placeholder="Email :" />
                    </div>
                </div>

                <div class="col-12">
                    <div class="mb-3">
                        <label for="" class="form-label fw-normal">Subject</label>
                        <input name="subject" id="subject" class="form-control" placeholder="subject :" />
                    </div>
                </div>

                <div class="col-12">
                    <div class="mb-3">
                        <label for="" class="form-label fw-normal">Comments <span class="text-danger">*</span></label>
                        <textarea name="comments" id="comments" rows={4} class="form-control" placeholder="Message :"></textarea>
                    </div>
                </div>
            </div>
            <div class="row">
                <div class="col-12">
                    <div class="d-grid">
                        <button type="submit" id="submit" name="send" class="btn btn-primary">Send Message</button>
                    </div>
                </div>
            </div>
        </form>
    </ModalBody>
</Modal>
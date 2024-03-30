<script>
import { onMount } from 'svelte';
import BackgroundImage from '../../../assets/images/bg/maintenance.jpg';
import Icon from '../../../assets/images/logo-icon-64.png';
onMount(() => {
    if(document.getElementById("maintenance")){
        var seconds = 3599;
        function secondPassed() {
            var minutes = Math.round((seconds - 30) / 60);
            var remainingSeconds = seconds % 60;
            if (remainingSeconds < 10) {
                remainingSeconds = "0" + remainingSeconds;
            }
            document.getElementById('maintenance').innerHTML = minutes + ":" + remainingSeconds;
            if (seconds == 0) {
                clearInterval(countdownTimer);
                document.getElementById('maintenance').innerHTML = "Buzz Buzz";
            } else {
                seconds--;
            }
        }
        var countdownTimer = setInterval(secondPassed, 1000);
    }
})
</script>

<section class="position-relative" style="background : url('{BackgroundImage}')">
    <div class="bg-overlay"></div>
    <div class="container-fluid">
        <div class="row">
            <div class="col-12 p-0">
                <div class="d-flex flex-column min-vh-100 px-md-5 py-5 px-4">
                    <div class="mt-md-5">
                        <a href="/"><img src={Icon} alt="" /></a>
                    </div>
                    <div class="title-heading my-auto">
                        <h4 class="text-white display-5 fw-bold mb-4">System is under maintenance</h4>
                        <p class="text-white-50 para-desc mb-4">Our design projects are fresh and simple and will benefit your business greatly. Learn more about our work!</p>
                        <span id="maintenance" class="timer h1 text-white"></span>
                        <span class="d-block h6 text-uppercase text-white-50">Minutes</span>
                    </div>
                    <div class="mb-md-5 footer">
                        <p class="mb-0 text-reset">© {(new Date().getFullYear())}{" "} Motos. Design with <i class="mdi mdi-heart text-danger"></i> by <a href={"#"} class="text-reset">Shreethemes</a>.</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>
<script setup>
import { ref } from "vue";

const formSubmitted = ref(false);

const submitForm = (event) => {
    event.preventDefault();
    formSubmitted.value = true;

    // Optional: Reset form after submission
    setTimeout(() => {
        formSubmitted.value = false;
    }, 3000);
};
</script>

<template>
    <div class="contact" id="contact">
        <div class="contact-card">
            <!-- Handshake Image -->
            <img src="/src/assets/images/handshake.png" alt="Handshake Illustration" class="handshake-img">

            <!-- Contact Form -->
            <div class="form-container">
                <h2>Contact.</h2>

                <form v-if="!formSubmitted" @submit="submitForm">
                    <input type="email" id="email" name="email" placeholder="Email" required />
                    <textarea id="message" name="message" rows="4" placeholder="Message" required></textarea>
                    <button type="submit">Send</button>
                </form>

                <!-- Thank You Message -->
                <p v-else class="thank-you-msg">Thank you for reaching out!</p>
            </div>
        </div>
    </div>
</template>

<style scoped>
.contact {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background: #f9f9f9;
    padding: 20px;
}

.contact-card {
    background: #fff;
    border-radius: 12px;
    padding: 30px;
    width: 100%;
    max-width: 400px;
    text-align: center;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.handshake-img {
    width: 100%;
    max-width: 250px;
    margin: 0 auto 20px;
}

.form-container h2 {
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 15px;
    color: #333;
}

input,
textarea {
    width: 100%;
    padding: 12px;
    margin-bottom: 15px;
    border: 1px solid #ddd;
    border-radius: 6px;
    font-size: 14px;
    transition: 0.3s;
}

input:focus,
textarea:focus {
    border-color: #e91e63;
    outline: none;
    box-shadow: 0 0 5px rgba(233, 30, 99, 0.2);
}

button {
    width: 100%;
    padding: 12px;
    background: #e91e63;
    color: #fff;
    font-size: 16px;
    font-weight: bold;
    border: none;
    border-radius: 6px;
    cursor: pointer;
    transition: 0.3s;
}

button:hover {
    background: #c2185b;
}

/* Thank You Message */
.thank-you-msg {
    font-size: 18px;
    color: #28a745;
    font-weight: bold;
    margin-top: 10px;
}
</style>

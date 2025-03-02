<script setup>
const data = [
    {
        id: 1,
        img: '/images/photo.png',
        msg: 'Working with King was an absolute pleasure! He exceeded expectations and delivered outstanding results.',
        user: 'Esther',
        post: 'CEO, S.U.E Enterprises'
    },
    {
        id: 2,
        img: '/images/pp.jpeg',
        msg: 'Professional, efficient, and detail-oriented. King transformed our project beautifully!',
        user: 'Mujahid',
        post: 'Founder, AppZeent.co'
    },
    {
        id: 3,
        img: '/images/photo.png',
        msg: 'King is a skilled developer who understands business needs. Highly recommend!',
        user: 'Ruth',
        post: 'Manager, Microsoft'
    }
];
</script>

<template>
    <div class="testimonials" id="testimonials">
        <h1>What Clients Say</h1>
        <div class="container">
            <div v-for="d in data" :key="d.id" class="card">
                <div class="top">
                    <i class="fa-brands fa-facebook"></i>
                    <img :src="d.img" alt="User Image">
                    <i class="fa-brands fa-twitter"></i>
                </div>

                <div class="center">
                    <p>"{{ d.msg }}"</p>
                </div>

                <div class="bottom">
                    <h3>{{ d.user }}</h3>
                    <h4>{{ d.post }}</h4>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.testimonials {
    background-color: white;
    text-align: center;
    padding: 60px 20px;
}

h1 {
    font-size: 42px;
    font-weight: bold;
    margin-bottom: 20px;
    color: #333;
}

.container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: center;
}

.card {
    width: 320px;
    background: #fafafa;
    border-radius: 10px;
    box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.1);
    padding: 25px;
    transition: transform 0.3s ease-in-out;
}

.card:hover {
    transform: translateY(-5px);
}

.top {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 15px;
    margin-bottom: 15px;
}

i {
    font-size: 20px;
    color: #888;
}

img {
    width: 70px;
    height: 70px;
    border-radius: 50%;
    object-fit: cover;
    border: 3px solid #e91e63;
}

.center {
    background: #fff5f7;
    padding: 15px;
    border-radius: 8px;
    font-size: 14px;
    font-style: italic;
    color: #444;
    margin-bottom: 20px;
}

.bottom h3 {
    margin-bottom: 5px;
    font-size: 18px;
    color: #222;
}

.bottom h4 {
    font-size: 14px;
    color: #777;
}
@media (max-width:768px) {
    h1{
        font-size: 20px;
    }
    .card{
        font-size: 500px;
    }
    .container{
        margin-left: -38px;
    }
}
</style>

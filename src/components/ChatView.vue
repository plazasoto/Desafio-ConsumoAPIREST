<template>
    <div class="col-6">
        <p class="message message--left bg-primary">mensaje L 1</p>
        <p class="message message--right bg-secondary">mensaje R 1</p>
        <p class="message message--right bg-secondary">mensaje R 2</p>
        <p class="message message--left bg-primary">mensaje L 2</p>
        <p class="message message--left bg-primary"> Lorem ipsum dolor sit amet consectetur adipisicing elit. Eum quod autem possimus vero ipsa delectus in, quis optio, quam eos pariatur quas ipsam quia error eius dignissimos reprehenderit minima obcaecati. </p>
    </div>
</template>

<script>
    //recibir los mensajes, hacerles un v-for con style binding segun user
</script>

<style scoped>
    .message{
        display: block;
        width: 50%;
        border-radius: 5px;
        text-align: center;
    }

    .message--left{
        /* text-align: left; */
        float:left;
        margin-right: 50%;
        /* background-color: ; */
    }
    
    .message--right{
        /* text-align: right; */
        float: right;
        margin-left: 50%;
    }
</style>
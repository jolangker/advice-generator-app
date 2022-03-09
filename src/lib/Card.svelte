<script>
    import dividerMobile from "../assets/images/pattern-divider-mobile.svg"
    import Dice from "./Dice.svelte";

    export let advice   
    export let adviceId
    export let rolling
</script>

<div class="card">
    <small>ADVICE #{adviceId}</small>
    <p>
        <q>{advice}</q>
    </p>
    <div class="divider">
        <img src="{dividerMobile}" alt="Mobile Divider">
    </div>
    <div class="dice-wrapper">
        <Dice on:roll {rolling}/>
    </div>
</div>

<style>
    .card {
        padding: 2rem 2rem 0rem 2rem;
        background-color: var(--dark-grayish-blue);
        border-radius: 8px;
        text-align: center;
        position: relative;
    }

    small {
        color : var(--neon-green);
        letter-spacing:0.25rem;
    }
    
    p{
        color: var(--light-cyan);
        font-size: 28px;
        margin-top: 1rem;
    }

    .divider {
        margin-top: 1rem;
    }

    .dice-wrapper{
        transform: translateY(2rem);
        width: max-content;
        margin: auto;
    }

    @media (min-width: 1024px) {
        .card{
            max-width: 400px;
            margin: auto;
        }
   }
</style>
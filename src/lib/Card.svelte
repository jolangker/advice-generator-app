<script>
    import dividerMobile from "../assets/images/pattern-divider-mobile.svg"
    import dividerDesktop from "../assets/images/pattern-divider-desktop.svg"
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
        <img src="{dividerMobile}" alt="Mobile Divider" class="mobile">
        <img src="{dividerDesktop}" alt="Desktop Divider" class="desktop">
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
        max-width: min-content;
        margin: auto;
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

   .mobile {
       display: block;    
   }

   .desktop {
       display: none;
   }

   @media (min-width: 1024px) {        
        .mobile {
           display: none;
       }

       .desktop {
           display: block;
       }
   }
</style>
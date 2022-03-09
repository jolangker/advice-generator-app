<script>
    import dice from "../assets/images/icon-dice.svg"
    import {createEventDispatcher} from "svelte"

    const dispatch = createEventDispatcher()

    const handleClick = ()=>{
        dispatch("roll")
    }

    export let rolling = false
</script>

<div class="dice" class:roll={rolling} on:click="{handleClick}">
    <img src="{dice}" alt="Icon Dice" >
</div>

<style>
    .dice {
        background-color: var(--neon-green);
        width: 2rem;
        height: 2rem;
        padding: 1rem;
        border-radius: 50%;
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;          
        cursor: pointer;
    }

    .roll {
        animation: rolling 750ms linear infinite;
        pointer-events: none;
    }

    @keyframes rolling {
        from {
            transform: rotate(0deg);
        }
        to{
            transform: rotate(360deg);
        }
    }
</style>
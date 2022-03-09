<script>
import Card from "./lib/Card.svelte";

let advice = ""
let adviceId = null

let isRolling = false

const randomQuote = async ()=>{
  isRolling = true
  try{    
    const res = await fetch("https://api.adviceslip.com/advice")
    const data = await res.json()
    advice = data.slip.advice
    adviceId = data.slip.id
  }catch(err){
    console.log(err);
  }finally{
    isRolling = false
  }  
} 

randomQuote()
</script>
<main>
  <Card {advice} {adviceId} on:roll="{randomQuote}" rolling={isRolling}/>
</main>

<style>
  main{
    padding: 4rem 1rem;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>

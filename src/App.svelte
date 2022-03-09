<script>
import Card from "./lib/Card.svelte";

let advice = "It is easy to sit up and take notice, what's difficult is getting up and taking and taking action."
let adviceId = 117

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

</script>
<main>
  <Card {advice} {adviceId} on:roll="{randomQuote}" rolling={isRolling}/>
</main>

<style>
  main{
    padding: 1rem;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>

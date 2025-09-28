<script lang='ts'>
    //with condition
    let score = $state(39);
    let grade = $derived(
        score < 39 ? "F":
        score < 59 ? "C":
        score < 79 ? "B":
        score <= 100 ? "A":"None"
    );

    //calculate
    let price = $state(40);
    let quantity = $state(2);
    let total = $derived(
        price * quantity
    );

</script>

<div><!--let newVar = $derived(expression depending on $state vars);-->
    <h1>This is Derived Page</h1><br/>
    <p>example 1:with condition</p>
    <p>score:{score},grade:{grade}</p><br/>

    <p>example 2:calculate </p>
    <p>price:{price}, quantity:{quantity} = total:{total}</p>
    <button onclick={()=>{quantity++}}>increase quantity</button>

    



</div>

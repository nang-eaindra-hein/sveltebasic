<script lang='ts'>
    type fruit={
        id:number;
        name:string;
        price:number;
        quantity:number;
    }

    const fruits: fruit[]=[
        {id:1011,name:"banana",price:40,quantity:20},
        {id:1020,name:"mango",price:60,quantity:18},
        {id:1062,name:"apple",price:54,quantity:21}
    ];
    const items: string[]=["banana","mango","apple"];
    

</script>

<div>
    <p>To view Fruit item details: Insert [ / + fruit's id number] behind /fruits</p>
    <br/>


    <ul><p>Today items are</p>
        {#each items as item,i}
        <li>{i+1}. {item} </li>
        {/each}
    </ul><br/>


        {#each fruits as fruit(fruit.id)}
        <div>
            <p>id: {fruit.id}, name: {fruit.name}</p>
            <p>price: {fruit.price}$, quantity:{fruit.quantity}</p><br/>
        </div>
        {/each}


</div>
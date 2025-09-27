<script lang='ts'>

    type clothe={
        id:number;
        types:string;
        price:number;
    }

    const animals: string[]=["cat","dog","bird"]; //ex1
    const tasks:string[]=[];      //ex2
    const clothes: clothe[]=[
        {id:101,types:"top",price:30},
        {id:103,types:"pants",price:53},
        {id:102,types:"hoodie",price:57}
    
    ] ;  //ex3

</script>

<ul>       <!--ex1-->
    {#each animals as animal,i}
    <li>{i+1}. {animal}</li>
    {/each}
    
</ul>

<div>      <!--ex2-->
    {#each tasks as task}
    <p>{task}</p>
    {:else}
    <p>no taks available</p>
    {/each}
</div>

<div>      <!--ex3-->
    {#each clothes as clothe(clothe.id)}
    <div>
        <h1>{clothe.types}</h1>
        <p>{clothe.price}</p>

    </div>
    {/each}

</div>


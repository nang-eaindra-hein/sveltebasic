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

    let isvisible = $state(false);
    let fruitDetails = $state(false);
    let fruitPrice = $state(false);
    

 
    class AddReset{
        addBanana = $state(0);
        mangoPrice = $state(60);
        applePrice = $state(54);
        bananaPrice = $state(40);

        addMango = $state(0);
        addApple = $state(0);
        addB(){
            this.addBanana++;
        }
        addM(){
            this.addMango++;
        }
        addA(){
            this.addApple++;
        }
        resetB(){
            this.addBanana=0;
        }
        resetM(){
            this.addMango=0;
        }
        resetA(){
            this.addApple=0;
        }
        totalPrice = $derived(
            addreset.addBanana * addreset.bananaPrice+
            addreset.addMango * addreset.mangoPrice+
            addreset.addApple * addreset.applePrice
        
        );
        bananaPriceTotal = $derived(
            addreset.addBanana * addreset.bananaPrice
        );
        mangoPriceTotal = $derived(
            addreset.addMango * addreset.mangoPrice
        );
        applePriceTotal = $derived(
            addreset.addApple * addreset.applePrice
        );

        totalQuantity = $derived(
            addreset.addBanana + addreset.addMango + addreset.addApple 
        );


    }
    const addreset = new AddReset();




    function modalOpen(){
        isvisible = !isvisible
    };
    function modalOpenFruit(){
        fruitDetails = !fruitDetails
    };
    function modalOpenPrice(){
        fruitPrice = !fruitPrice
    };
    

</script>

<div>
    <p>To view Fruit item details: Insert [ / + fruit's id number] behind /fruits</p>
    <br/>
    


    <div>
        <button onclick={modalOpen}>click to view today's items<br/>
            {isvisible ? "Hide":"Show"}

        </button>
        {#if isvisible}
        <ul><p>Today items are</p>
            {#each items as item,i}
            <li>{i+1}. {item} </li>
            {/each}
        </ul>
     
        {/if}
    </div><br/>
    

    <div>
        <botton onclick={modalOpenFruit}>Click to view fruits' details <br/>

            {fruitDetails ? "Hide":"Show"}

        </botton>
        {#if fruitDetails}
        <h1>Fruits' Details</h1><br/>
        {#each fruits as fruit(fruit.id)}
        <div>
            <p>id: {fruit.id}, name: {fruit.name}</p>
            <p>price: {fruit.price}$, quantity:{fruit.quantity}</p><br/>
            
        </div>
        {/each}
        <h2>Add To Cart Session</h2>
        <p>Banana({addreset.addBanana})</p>
        <button onclick={()=>addreset.addB()}>Add to Cart

        </button>
        <p><button onclick={()=>addreset.resetB()}>reset

        </button>
        </p><br/>

        <p>mango({addreset.addMango})</p>
        <button onclick={()=>addreset.addM()}>Add to Cart

        </button>
        <p><button onclick={()=>addreset.resetM()}>reset

        </button>
        </p><br/>


        <p>apple({addreset.addApple})</p>
        <button onclick={()=>addreset.addA()}>Add to Cart

        </button>
        <p><button onclick={()=>addreset.resetA()}>reset

        </button>
        </p><br/>

        {/if}
    </div><br/>

    
    <div>
        <botton onclick={modalOpenPrice}>Checkout <br/>
            {fruitPrice ? "Hide": "Show"}
        </botton>
        {#if fruitPrice}
        <h1>Total</h1>
        <p>items quantity:Banana:{addreset.addBanana},${addreset.bananaPriceTotal}/Mango:{addreset.addMango},${addreset.mangoPriceTotal}/Apple:{addreset.addApple},${addreset.applePriceTotal}</p>
        <p>total quantity:{addreset.totalQuantity}</p>
        <p>total price:{addreset.totalPrice}</p>
        






        {/if}

    </div>
        
<br/>

    

    


</div>
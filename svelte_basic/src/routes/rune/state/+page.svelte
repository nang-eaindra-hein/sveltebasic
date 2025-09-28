<script lang='ts'>  

    let count = $state(0);  //number
    let name =$state("Nang") //str
    let isvisible = $state(false)  //bool
    let user = $state({name:"Nang",age:18}) //obj
    let fruits = $state(["banana","apple"])  //arrays

    class Counter{        //class
        count = $state(0);
        increment(){
            this.count++;
        }
        reset(){
            this.count=0;
        }
    }
    const counter = new Counter(); //muct go with "counter."

    let numberx = $state(3);  //for return
    let numbery = $state(40);
    

    function changeName(){  //str
        name = "Clara";    //rerender UI instantly
    }

    function modal(){        //bool
        isvisible = !isvisible;  //show,not visible
    }

    function ageplus(){       //obj
        user.age++;      //age plus 1
    }

    function addfruit(){     //arrays
        fruits = [...fruits,"peach"]    //add peach
    }

    function multiply():number{    //number=int m lo
        return numberx * numbery;   //multi return

    }

    function square():number{
        return numberx * numberx;   //sqr return
    }


</script>

<div><!--let variableName = $state(initialValue-num,str,bool,obj,arr)-->
    <h1>$State Page </h1><br/>

        <p> example 1: number </p>
        <p><button onclick={()=>count++}>Click: {count}

        </button></p><br/>

        <p>example 2: strings</p> 

        <h2>my name is {name}</h2>

        <p><button onclick={changeName}>Change Name
        </button></p><br/>

        <p>example 3:boolean</p>
        <button onclick={modal}>
            {isvisible ? "Hide" : "show" }
        </button>
        {#if isvisible}
        <p>this text is visible</p>
        {:else}
        <p>this text is not visible</p>
        {/if}<br/>

        <p>example 4:object</p>
        <p>{user.name} is {user.age}!</p>
        <p><button onclick={ageplus}>Click to plus age.

        </button></p><br/>

        <p>example 5:array</p>
        {#each fruits as fruit}
        <p>{fruit}</p>
        {/each}
        <p><button onclick={addfruit}>add fruit

        </button></p><br/>

        <p>example 6:class</p>
        <p>Count:{counter.count}</p>
        <button onclick={()=>counter.increment()}>Click to increase number</button><br/>
        <p><button onclick={()=>counter.reset()}>reset</button></p><br/>

        <p>example 7:return</p>
        <p>for multiplication---{numberx} into {numbery} = {multiply()}</p>
        <p>for square----{numberx}into {numberx} = {square()}</p><br/>
   
</div>



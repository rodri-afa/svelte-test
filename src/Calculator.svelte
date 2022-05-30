<script>

    const numeros={
        n1:'',
        n2:''
    }
    let op=''
    let resultado =''

    const botones=[
        {
            operacion:'suma',
            click: ()=>op='+',
            simbolo: '+',
        },{
            operacion:'resta',
            click: ()=>op='-',
            simbolo: '-',
        },{
            operacion:'multiplicacion',
            click: ()=>op='*',
            simbolo: '*',
        },{
            operacion:'division',
            click: ()=>op='/',
            simbolo: '/',
        }
    ]

    function addTerm(el){
        let value =el.srcElement.value.toString() 
        
        if(value =='.'&& numeros[numActivo].includes('.')) numeros[numActivo]=numeros[numActivo] 
        else numeros[numActivo]+=value
    }
    function clear(){
        numeros.n1=''
        numeros.n2=''
        op = ''
        resultado=''
    }
    function calculate(){
        numeros.n1=parseFloat(numeros.n1)
        numeros.n2=parseFloat(numeros.n2)

        switch (op) {
            case '+':
                resultado = numeros.n1+numeros.n2
                break
            case '-':
                resultado = numeros.n1-numeros.n2
                break
            case '*':
                resultado = numeros.n1*numeros.n2
                break
            case '/':
                resultado = numeros.n1/numeros.n2
                break
        
            default:
                break
        }
        resultado.toFixed(2)
    }
    
    $: numActivo = op == ''? 'n1':'n2'

</script>

<div id="calculator">
    <div id="display">
        <div id="operaciones">
            <span>{numeros.n1}</span>
            <span>{op}</span>
            <span>{numeros.n2}</span>
        </div>
        <div  id="resultado">{resultado}</div>
    </div>

    <div id="numbers">
        <button on:click="{addTerm}" value="1">1</button>
        <button on:click="{addTerm}" value="2">2</button>
        <button on:click="{addTerm}" value="3">3</button>
        <button on:click="{addTerm}" value="4">4</button>
        <button on:click="{addTerm}" value="5">5</button>
        <button on:click="{addTerm}" value="6">6</button>
        <button on:click="{addTerm}" value="7">7</button>
        <button on:click="{addTerm}" value="8">8</button>
        <button on:click="{addTerm}" value="9">9</button>
        <button on:click="{addTerm}" value="0">0</button>
        <br>
        
        <button on:click="{addTerm}" value=".">.</button>
        <button on:click="{clear}">clear</button>
        <button on:click="{()=> op = '+'}" >+</button>
        <button on:click="{()=> op = '-'}" >-</button>
        <button on:click="{()=> op = '*'}" >x</button>
        <button on:click="{()=> op = '/'}" >/</button>


        <!-- {#each botones as boton}
        <button on:click="{boton.funcion}" value="{boton.simbolo}">{boton.simbolo}</button>
        {/each} -->
        <button on:click="{calculate}" >=</button>
    </div>
</div>

<style>
    #calculator{
        max-width: 400px;
        margin: auto;
    }
    #display{
        border: 1px solid gray;
        margin-bottom: 12px;
    }
    #operaciones, #resultado{
        min-height: 24px;
    }

</style>
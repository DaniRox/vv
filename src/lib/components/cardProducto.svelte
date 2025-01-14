<script>
    export let fotoProducto = "#";
    export let titulo = "titulo";
    export let precio = "precioUnitario";
    export let descripcion = "descripcion";
    export let stock = 1;
    export let cantidad = 1;

    // Función para incrementar la cantidad
    function incrementar() {
        if (cantidad < parseInt(stock)) {
            cantidad = parseInt(cantidad) + 1;
        }
    }

    // Función para decrementar la cantidad
    function decrementar() {
        if (cantidad > 1) {
            cantidad = parseInt(cantidad) - 1;
        }
    }
</script>


<style>
    .cardProducto {
        width: 100%;
        padding: 1rem;
        gap: 2rem;
        display: flex;
        flex-direction: column;
    }

    .tituloMovil{
        font-weight: 500;
        font-size: 1.2rem;
    }

    .tituloEscritorio {
        display: none;
        font-weight: 500;
        font-size: 1.2rem;
    }

    .fotosProducto {
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .miniaturas {
        display: none;
    }
    
    .foto {
        width: 100%;
        height: 16rem;
        display: flex;
        justify-content: center;
        align-items: flex-end;
        overflow: hidden;
    }

    img {
        height: 100%;
        max-width: none;
    }

    .infoProducto {
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }

    .infoProducto-text {
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }
    .spanPrecio {
        font-size: 1.6rem;
        font-weight: 400;
    }

    .descripcion {
        font-size: 0.9rem;
        font-weight: 300;
    }

    .spanUnidades {
        font-size: 0.8rem;
        font-weight: 600;
        color: var(--plant);
    }

    .compra {
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }
    .botones {
        display: flex;
        flex-direction: row;
        gap: 1rem;
    }

    .botonesCantidad {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        border: 2px solid var(--plantlithe);
        width: min-content;
        height: 2.2rem;
        border-radius: 0.8rem;
    }
    .btnCantidad {
        width: auto;
        padding: 0.1rem;
    }
    .btnIcon {
        width: 1.6rem;
    }

    .divCantidad {
        width: 2.4rem;
        height: 100%;
        padding: 0.1rem;
        display: flex;
        align-items: center;
        justify-content: center;
        border-right: 2px solid var(--plantlithe);
        border-left: 2px solid var(--plantlithe);
    }

    .btnCarrito {
        height: 2.2rem;
        background-color: var(--plantlithe);
        padding: 0.5rem 0.8rem;
        border-radius: 0.8rem;
        font-size: 1rem;
        font-weight: 500;
    }


    @media (min-width: 768px){
        .cardProducto {
            flex-direction: row;
        }

        .tituloMovil{
            display: none;
        }

        .tituloEscritorio {
            display: flex;
        }

        .fotosProducto {
            width: 50%;
        }

        .infoProducto {
            justify-content: space-between;
        }

        .botones {
            gap: 2.5rem;
        }
    }

</style>


<div class="cardProducto">
    <h1 class="tituloMovil">{titulo}</h1>

    <div class="fotosProducto">
        <div class="miniaturas"></div>
        <div class="foto">
            <img src={fotoProducto} alt="">
        </div>
    </div>

    <div class="infoProducto">
        <div class="infoProducto-text">
            <h1 class="tituloEscritorio">{titulo}</h1>
            <p class="descripcion"> {descripcion}</p>
        </div>
        

        <div class="compra">
            <span class="spanPrecio">${precio}</span>
            <span class="spanUnidades">{stock} disponibles</span>
            <div class="botones">
                <div class="botonesCantidad">
                    <button class="btnCantidad" id="menos" on:click={decrementar}>
                        <img src="/img/BiDash.svg" alt="" class="btnIcon">
                    </button>
                    <div class="divCantidad">{cantidad}</div>
                    <button class="btnCantidad" id="mas" on:click={incrementar}>
                        <img src="/img/BiPlus.svg" alt="" class="btnIcon">
                    </button>
                </div>
                <button class="btnCarrito">Agregar al carrito</button>
            </div>
        </div>
    </div>
</div>
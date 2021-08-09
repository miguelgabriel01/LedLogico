<script>
    //variavel para armazenar os ids de cada cubo(temporariamente)
    let cubosId = [
        false,false,false,false,false,false,false,false,false,false,
        false,false,false,false,false,false,false,false,false,false,
        false,false,false,false,false,false,false,false,false,false,
        false,false,false,false,false,false,false,false,false,false,
        false,false,false,false,false,false,false,false,false,false,
        false,false,false,false,false,false,false,false,false,false,
        false,false,false,false
    ];

    //cores padrão dos cubos
    let corCuboSelecionado = '#0a2f35';//cor do cubo selecionado
    let corCubospadrao = 'whitesmoke';//valor inicial do cubo

    //função que recebe o evento que diz qual cubo foi clicado pelo usuario
    function handleClickCubo(id) {
        alert("O indice clicado foi: " + id);
        console.log(id);

        /**
        verofocamos se o valor recebido como
         parametro é false, se for, alteramos para true e o mesmo acontece se o valor for true
        */
        if(cubosId[id] === false){
            cubosId[id] = true
        }else{
            cubosId[id] = false
        }
        console.log(cubosId);
    }

    let modalAtivo = false;
    let modalDisplay = 'none'


 function handleModal(){
    let modalAtivo = true;
     alert('Apertou no modal')
     if(modalAtivo === true){
        modalDisplay = 'flex'
    }else{
        modalDisplay = 'none'
    }
 }

</script>

    <input type="checkbox" name="" id="light-css" style="display: none;" />
    <main>
        <audio id="audio" autoplay>
            <source
                src="./public/music/musicaTema.mp3"
                type="audio/mp3"
                loop="infinit"
            /> Seu navegador não possui suporte ao elemento audio
        </audio>
        <!-- Input responsavel por ativar o modo claro  -->
        <nav class="leds" style="display: non;">
            {#each cubosId as cubo, i}
            {#if cubo === false}
                <div on:click={() => handleClickCubo(i)} id="led" style="background:{corCubospadrao};" />
                    
                    {/if}
                    {#if cubo === true}
                    <div on:click={() => handleClickCubo(i)} id="led" style="background:{corCuboSelecionado};" />
                        {/if}
                    {/each}

        </nav>

        <div class="jogador">
            <img src='imagens/avatares/user.jpg' alt="jogador" class="player" />

            <div class="pontuacaoHome">
                <div class="iconeVida" />
                <div class="porcentagem" />
            </div>

            <a hsref="#modal" class="buttonOpcoes" on:click={handleModal}
                ><img
                    src="imagens/icones/menu_white_36dp.svg"
                    alt="opções"
                    style="margin-top: 10px;"
                /></a
            >
        </div>

        <div class="modal" id="modal" tabindex="-1" style="border:1px solid red; display:{modalDisplay} ">
            <a href="#" class="modal__overlay" aria-label="Fechar" />
            <div class="modal__content">
                <div class="opMenu">
                    <div class="pontuacao">
                        <div class="infoVida">
                            <div class="iconeVida" />
                            <div class="vida" />
                        </div>
                        <!--         <small class="pontos">48</small>
-->
                        <h3 class="objetivo">OBJETIVO PRINCIPAL</h3>
                        <p id="descricaoObjetivo">
                            Destruir todos os cubos com o menor numero de
                            movimentos possíveis e derrotar o <b>REI DE GELO.</b
                            ><br />
                            Mas não é tão fácil como parece, se você for derrotado,
                            o mundo entrará em sua era de extinção. <br />
                            Sua vida esta limitada, por isso utilize o menor numero
                            de movimentos para destruir todos os cubos.<br />
                            Boa sorte e que os <b>DEUSES TE PROTEJAM.</b>
                        </p>
                        <div id="barrainferior" />

                        <div class="poderesOP">
                            <div class="poderOP1" />
                            <div class="poderOP2" />
                            <div class="poderOP3" />
                            <div class="poderOP4" />
                            <div class="poderOP5" />
                        </div>
                    </div>
                    <div class="configuracoes">
                        <nav class="menupause">
                            <a class="buttonContinuar" href="#">CONTINUAR</a>
                            <!--               <a class="buttonContinuar" href="home.html">REINICIAR</a>
-->
                            <label for="light-css" style="cursor: pointer;">
                                <p class="buttonReiniciar">MODO DARK</p>
                            </label>
                            <a class="buttonSair" href="#/">SAIR</a>
                        </nav>
                    </div>
                </div>
            </div>
        </div>
    </main>

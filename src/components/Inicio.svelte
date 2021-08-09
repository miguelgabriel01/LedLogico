<script>
    //variavel para armazenar os ids de cada cubo(temporariamente)
    let cubosId = [
        1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20,
        21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38,
        39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56,
        57, 58, 59, 60, 61, 62, 63, 64,
    ];
    console.log(cubosId);

    //função que recebe o evento que diz qual cubo foi clicado pelo usuario
    function handleClickCubo(id) {
        alert("O indice clicado foi: " + id);
        console.log(id);
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
                <div on:click={() => handleClickCubo(cubo)} id="led" />
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

<script>
    import { onMount } from "svelte"; //importamos o ciclo de vida que é ativado assim que o usuario entra no jogo( assim que o componente é montado)

    //variavel para armazenar os ids de cada cubo(temporariamente)
    let cubosId = [
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
        false,
    ];

    let cubosAtivos = []; //array para armazenar quais cubos estão ativos no momento
    //valores dos lados dos cubos
    const ladoEsquerdoIndex = [0, 8, 16, 24, 32, 40, 48, 56]; //indices do lado esquerdo
    const ladoDireitoIndex = [7, 15, 23, 31, 39, 47, 55, 63]; //inices do lado direito

    //cores padrão dos cubos whitesmoke
    let corCuboSelecionado = "whitesmoke"; //cor do cubo selecionado
    let corCubospadrao = "#0a2f35"; //valor inicial do cubo

    //parte relacionada ao modal( não editar pq agora n é importante)
    let modalAtivo = false;

    //função que verifica os valores recebidos e ativa ou desativa os cubos
    function handleAtivo(id, estado) {
        //verificamos se o valor recebido como parametro está no lado esquerdo usando o id recebido como parametro
        if (ladoEsquerdoIndex.indexOf(id) > -1) {
            cubosAtivos = [id, id + 1, id + 8, id - 8];
            for (var i = 0; i < cubosAtivos.length; i++) {
                //condição para verificar e não permitir que novos cubos sejam criados
                if (cubosAtivos[i] >= 0 && cubosAtivos[i] <= 63) {
                    cubosId[cubosAtivos[i]] = !cubosId[cubosAtivos[i]]; //estado; //fazemos a atribuição dos valores de acordo com os indeces que foram gerados
                }
            }
        }
        //verificamos se o valor recebido como parametro está no lado direito usando o id recebido como parametro
        else if (ladoDireitoIndex.indexOf(id) > -1) {
            cubosAtivos = [id, id - 1, id + 8, id - 8];
            for (var i = 0; i < cubosAtivos.length; i++) {
                //condição para verificar e não permitir que novos cubos sejam criados
                if (cubosAtivos[i] >= 0 && cubosAtivos[i] <= 63) {
                    cubosId[cubosAtivos[i]] = !cubosId[cubosAtivos[i]]; //estado; //fazemos a atribuição dos valores de acordo com os indeces que foram gerados
                }
            }
        }
        //se não estiver nem no lado direito ou no lado esquerdo, ele estará no meio
        else {
            cubosAtivos = [id, id - 1, id + 1, id - 8, id + 8];
            for (var i = 0; i < cubosAtivos.length; i++) {
                //condição para verificar e não permitir que novos cubos sejam criados
                if (cubosAtivos[i] >= 0 && cubosAtivos[i] <= 63) {
                    cubosId[cubosAtivos[i]] = !cubosId[cubosAtivos[i]]; //estado; //fazemos a atribuição dos valores de acordo com os indeces que foram gerados
                }
            }
        }

        //verificamos o estado do jogo
        for (let i = 0; i < cubosId.length; i++) {
            //procura dentro do array(cubosId) algum valor false( que significa que o jogo ainda deve continuar = um led apagado)
            if (cubosId.includes(false)) {
                //nada acontece se o array ainda possuir valores falses
            } else {
                return handleVitoria(true); //caso ele não entre na condição que verifica um valor false, ele vem para o else que chama a função handleVitoria e passa como parametro o valor true
            }
        }
    }

    //função que recebe o evento que diz qual cubo foi clicado pelo usuario
    function handleClickCubo(id) {
        /**
        verificamos se o valor recebido como
         parametro é false, se for, alteramos para true e o mesmo acontece se o valor for true
        */
        if (cubosId[id] === false) {
            return handleAtivo(id, true);
        }
        //entra aqui caso o cubo já esteja ativo(true)
        else {
            return handleAtivo(id, false);
        }
    }

    //Função que verifica/recebe o status do jogo e faz a proxima ação!!
    function handleVitoria(status) {
        if (status === true) {
            //verificamos se o valor recebido como parametro é verdadeiro
            //voltamos os cubos ao estado original( false )
            for (let i = 0; i < cubosId.length; i++) {
                cubosId[i] = false; //apos o usuario ter ganho o jogo, todos os cubos voltam para o valor original(false)
                window.location.href = "#/venceu"; //o usuario é redirecionado para o componente que mostra que que ele venceu e dá a opção de retornar ao menu
            }
        }
    }

    function handleDerrota() {
        //redirecionamos em caso de derrota( só será iniciado apos o primeiro clique)
        setTimeout(function () {
            window.location.href = "#/perdeu";
        }, 100000); //x segundos
    }

    //ciclo de vida que é ativado assim que o componente é iniciado!!!!
    onMount(async () => {
        await handleDerrota();
    });

    //função para gerenciar o modal
    function handleModal() {
        modalAtivo = !modalAtivo;
    }
</script>

<input type="checkbox" name="" id="light-css" style="display: none;" />
<main>
    <audio id="audio" autoplay>
        <source
            src="/music/musicaTema.mp3"
            type="audio/mp3"
            loop="infinit" />
        Seu navegador não possui suporte ao elemento audio
    </audio>
    <!-- Input responsavel por ativar o modo claro  -->
    <nav class="leds" style="display: non;">
        {#each cubosId as cubo, i}
            {#if cubo === false}
                <div
                    id="led"
                    on:click={() => handleClickCubo(i)}
                    style="background:{corCubospadrao};" />
            {/if}
            {#if cubo === true}
                <div
                    on:click={() => handleClickCubo(i)}
                    id="led"
                    style="background:{corCuboSelecionado};" />
            {/if}
        {/each}
    </nav>

    <div class="jogador">
        <img src="imagens/avatares/user.jpg" alt="jogador" class="player" />

        <div class="pontuacaoHome">
            <div class="iconeVida" />
            <div class="time">
                <div class="porcentagem" />
            </div>
        </div>

        <a hsref="#modal" class="buttonOpcoes" on:click={handleModal}><img
                src="imagens/icones/menu_white_36dp.svg"
                alt="opções"
                style="margin-top: 10px;" /></a>
    </div>
    {#if modalAtivo == true}
        <div
            class="modal"
            id="modal"
            tabindex="-1"
            style="
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction:column;
">
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
                            movimentos possíveis e derrotar o
                            <b>REI DE GELO.</b><br />
                            Mas não é tão fácil como parece, se você for
                            derrotado, o mundo entrará em sua era de extinção.
                            <br />
                            Sua vida esta limitada, por isso utilize o menor
                            numero de movimentos para destruir todos os cubos.<br />
                            Boa sorte e que os
                            <b>DEUSES TE PROTEJAM.</b>
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
                            <a
                                class="buttonContinuar"
                                on:click={handleModal}
                                style="cursor:pointer">CONTINUAR</a>
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
    {/if}
</main>

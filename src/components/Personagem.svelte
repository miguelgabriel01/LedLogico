<script>


import { nomeHeroi } from "../store";



    let herois = [
        {
            nome: "Peter apostle",
            foto: "/imagens/avatares/heroi01.jpg",
            descricao:
                "Desbravador, participou da conquista dos 7 reinos junto com seu irmão que foi morto pelo rei de gelo. seu unico desejo é a vingança",
        },
        {
            nome: "Matthew apostle",
            foto: "/imagens/avatares/heroi2.jpg",
            descricao:
                "Destemido, sobrevivente do atentado a seu reino comandado pelo genral Arios onde feriu um dos seus olhos",
        },
        {
            nome: "Mary",
            foto: "/imagens/avatares/heroi3.jpg",
            descricao:
                "Herdera de um reino conquistado por Mathias, luta pela independencia do seu povo com verdade e justiça",
        },
        {
            nome: "traitor judas",
            foto: "/imagens/avatares/heroi4.jpg",
            descricao:
                "Arrependido, lutou nos exercitos do Oeste que eram comandado pelo aliado de Mathias, o lord Elion",
        },
        {
            nome: "Thiago apostle",
            foto: "/imagens/avatares/heroi5.jpg",
            descricao:
                "Santo, o homem mais proximo dos deuses e responsavel por guadar o livro dos salvos para ressucitar os homens",
        },
        {
            nome: "Paul the persecutor",
            foto: "/imagens/avatares/heroi6.jpg",
            descricao:
                "Cruel e Honrado, responsavel por matar o herdeiro do trono do inferno e roubar o livro dos mortos",
        },
        {
            nome: "Andrew apostle",
            foto: "/imagens/avatares/heroi7.jpg",
            descricao:
                "Lider, junto com Peter, foi responsavel por destruir as mulharas de gelo do reino perdido e levar paz ao povo",
        },
        {
            nome: "john Baptist",
            foto: "/imagens/avatares/heroi8.jpg",
            descricao:
                "Sabio, agraçiado com o poder sabedoria dos homens e a força dos arcanjos que não se curvaram na grande batalha.",
        },
    ];

    //altera o nome do heroi de acordo com a escolha do usuario
    function handleHeroi(nome) {
        nomeHeroi.set(nome);
        window.location.href = "#/jogar/";
    }
</script>

<div class="escolherPersonagem">
    <h2 class="tituloHeroi">Escolha seu heroi!!</h2>
    <div class="personagem">
        {#each herois as heroi, i}
            <div class="heroi" on:click={() => handleHeroi(heroi.nome)}>
                <img src={heroi.foto} alt="" class="fotoHeroi" />
                <h2 class="nomeHeroi">{heroi.nome}</h2>
                <p class="descricaoHeroi">{heroi.descricao}</p>

                <div class="poderesOPHeroi">
                    <div class="poderOP1Heroi" />
                    <div class="poderOP2Heroi" />
                    <div class="poderOP3Heroi" />
                    <div class="poderOP4Heroi" />
                    <div class="poderOP5Heroi" />
                </div>
            </div>
        {/each}
    </div>
</div>




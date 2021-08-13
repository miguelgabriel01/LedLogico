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
                "Desbravador, participou da conquista dos 7 reinos junto com seu irmão que foi morto pelo rei de gelo. seu unico desejo é a vingança",
        },
        {
            nome: "Mary",
            foto: "/imagens/avatares/heroi3.jpg",
            descricao:
                "Desbravador, participou da conquista dos 7 reinos junto com seu irmão que foi morto pelo rei de gelo. seu unico desejo é a vingança",
        },
        {
            nome: "traitor judas",
            foto: "/imagens/avatares/heroi4.jpg",
            descricao:
                "Desbravador, participou da conquista dos 7 reinos junto com seu irmão que foi morto pelo rei de gelo. seu unico desejo é a vingança",
        },
        {
            nome: "Thiago apostle",
            foto: "/imagens/avatares/heroi5.jpg",
            descricao:
                "Desbravador, participou da conquista dos 7 reinos junto com seu irmão que foi morto pelo rei de gelo. seu unico desejo é a vingança",
        },
        {
            nome: "Paul the persecutor",
            foto: "/imagens/avatares/heroi6.jpg",
            descricao:
                "Desbravador, participou da conquista dos 7 reinos junto com seu irmão que foi morto pelo rei de gelo. seu unico desejo é a vingança",
        },
        {
            nome: "Andrew apostle",
            foto: "/imagens/avatares/heroi7.jpg",
            descricao:
                "Desbravador, participou da conquista dos 7 reinos junto com seu irmão que foi morto pelo rei de gelo. seu unico desejo é a vingança",
        },
        {
            nome: "john Baptist",
            foto: "/imagens/avatares/heroi8.jpg",
            descricao:
                "Desbravador, participou da conquista dos 7 reinos junto com seu irmão que foi morto pelo rei de gelo. seu unico desejo é a vingança",
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




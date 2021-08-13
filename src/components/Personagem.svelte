<script>
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
</script>

<div class="escolherPersonagem">
    <h2 class="tituloHeroi">Escolha seu heroi!!</h2>

    <div class="personagem">
        {#each herois as heroi, i}
            <div class="heroi">
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

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    .tituloHeroi {
        color: white;
        font-family: "Cinzel Decorative", cursive;
    }

    .escolherPersonagem {
        width: 100%;
        height: 100%;

        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;

        padding: 10px;

        background-color: black;
    }

    .personagem {
        width: 100%;
        height: 100%;
        border: 1px solid black;

        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: row;
        flex-wrap: wrap;
    }

    .heroi {
        width: 380px;
        height: 470px;

        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }

    .fotoHeroi {
        width: 300px;
        height: 320px;
        transition: all;
    }

    .fotoHeroi:hover {
        width: 305px;
        height: 325px;
    }

    .nomeHeroi {
        color: whitesmoke;
        font-family: "Cinzel Decorative", cursive;
        margin-top: 15px;
        font-size: 18px;
    }

    .descricaoHeroi {
        width: 350px;
        color: whitesmoke;
        font-size: 15px;
        text-align: center;
    }

    .poderesOPHeroi {
        width: 200px;
        height: 20px;
        display: flex;
        justify-content: space-around;
        align-items: center;
        flex-direction: row;
        margin-top: 20px;
    }

    .poderOP1Heroi {
        width: 15px;
        height: 15px;
        background-image: var(--icone-umStatus);
        background-repeat: no-repeat;
        background-size: cover;
    }

    .poderOP2Heroi {
        width: 15px;
        height: 15px;
        background-image: var(--icone-doisStatus);
        background-repeat: no-repeat;
        background-size: cover;
    }

    .poderOP3Heroi {
        width: 15px;
        height: 15px;
        background-image: var(--icone-tresStatus);
        background-repeat: no-repeat;
        background-size: cover;
    }

    .poderOP4Heroi {
        width: 15px;
        height: 15px;
        background-image: var(--icone-quatroStatus);
        background-repeat: no-repeat;
        background-size: cover;
    }

    .poderOP5Heroi {
        width: 15px;
        height: 15px;
        background-image: var(--icone-cincoStatus);
        background-repeat: no-repeat;
        background-size: cover;
    }
</style>

<script>
    let membros = [
        {
            foto: "/imagens/integrantes/aline.png",
            descricao: "Alline Desenvolvedora",
            github: "https://github.com/Anne951",
            nome: "Alline",
        },
        {
            foto: "/imagens/integrantes/ivan.png",
            descricao: "Ivan Desenvolvedor",
            github: "https://github.com/ivan-teotonio",
            nome: "Ivan",
        },
        {
            foto: "/imagens/integrantes/miguel.png",
            descricao: "Miguel Desenvolvedor",
            github: "https://github.com/miguelgabriel01",
            nome: "Miguel",
        },
        {
            foto: "/imagens/integrantes/leandro.png",
            descricao: "Leandro Desenvolvedor",
            github: "https://github.com/ljdossantos",
            nome: "Leandro",
        },
        {
            foto:
                "/imagens/integrantes/WhatsApp Image 2021-07-06 at 21.45.34.jpeg",
            descricao: "Luan Desenvolvedor",
            github: "https://github.com/Luanjoss",
            nome: "Luan",
        },
        {
            foto:
                "/imagens/integrantes//WhatsApp Image 2021-07-06 at 21.31.35.jpeg",
            descricao: "Denis Desenvolvedor",
            github: "https://github.com/LOCOBURGUE",
            nome: "Denis",
        },
        {
            foto:
                "/imagens/integrantes/WhatsApp Image 2021-07-07 at 12.39.50.jpeg",
            descricao: "Haendel Desenvolvedor",
            github: "https://github.com/Haendelima",
            nome: "Haendel",
        },
    ];
</script>

<section>
    <h1 class="title">DEVELOPER TEAM</h1>
    <div class="text">
        <p>
            Equipe responsável pelo desenvolvimento do jogo LedLógico da cadeira
            de lógica de programação do curso Tecnologia em Sistemas para
            Internet/ Informática para a internet.
        </p>
        <a class="buttonContinuar2" href="#/">MENU</a>
    </div>
    <div class="team-row">
        {#each membros as membro, i}
            <div class="member">
                <img src={membro.foto} alt={membro.descricao} />
                <h2>{membro.nome}</h2>
                <p><a href={membro.github} target="_blank">GitHub</a></p>
            </div>
        {/each}
    </div>
</section>

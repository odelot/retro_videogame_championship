
# retro_videogame_championship
[![en](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/odelot/retro_videogame_championship/blob/main/README.md)

## O que é?

Este é um web app standalone (funciona offline) criado para ajudar entusiastas de jogos retrô a organizarem sorteios para campeonatos. O app sorteia consoles, jogos e adversários, incentivando os jogadores a saírem da zona de conforto.

Inspirado no caos divertido do "Chance Time" do *Mario Party*, o app traz uma mecânica similar: um participante é escolhido para girar a roleta e definir o console, número de jogadores, adversários e o jogo que será jogado.

🎥 **Veja o vídeo demo:**

[![Watch the video](https://img.youtube.com/vi/9I7slwqLqHQ/hqdefault.jpg)](https://youtube.com/shorts/9I7slwqLqHQ)

Gostou da ideia? Se divertiu usando? Tem sugestões de novas funcionalidades? Considere pagar uma breja! 🍺 ^.^

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/odelot)

---

### Aviso

Este projeto começou como uma ideia rápida e simples para nosso evento de jogos retrô. Tudo — HTML, CSS e JavaScript — está em um único arquivo `index.html`. Se quiser ajudar a melhorar o código, fique à vontade para abrir um pull request. Obrigado!

---

## Como Configurar

Edite as listas JSON no final do arquivo `index.html` para personalizar seu campeonato.

### Passo 1: Adicione Participantes

Substitua os nomes e imagens de perfil no array `participantes`:
```javascript
let evento = {    
    participantes: [
      { nome: "Blake Lively", rodada1: 0, rodada2: 0, rodada3: 0, rodada4:0,  total: 0, profileImg: "blake.png" },
      { nome: "Tom Hanks", rodada1: 0, rodada2: 0, rodada3: 0, rodada4:0, total: 0, profileImg: "tom.png" },
      // Adicione mais participantes conforme necessário
    ],
    rodadaAtual: 1,
    rodadas: new Array(4),
};
```
Cada participante precisa de:
- `nome`: Nome do jogador.
- `profileImg`: Caminho para a imagem (tamanho recomendado: 195x177px).

### Passo 2: Adicione Consoles

Atualize o array `listaDeVideoGames` com os consoles do evento:
```javascript
const listaDeVideoGames = [
    { nome: "Dreamcast", imagem: "dreamcast.png" },
    { nome: "GameCube", imagem: "gamecube.png" },
    // Adicione mais consoles conforme necessário
];
```

### Passo 3: Adicione Jogos

Defina os jogos para cada console no array `jogos`:
```javascript
const jogos = [
    { console: "SNES", estacao: "x2", jogo: "Mario Kart", desc: "" },
    { console: "PS1", estacao: "x2", jogo: "Tekken 3", desc: "Melhor de 3 rodadas." },
    // Adicione mais jogos conforme necessário
];
```
- `console`: Deve corresponder a um nome no `listaDeVideoGames`.
- `estacao`: Número de jogadores (`x2`, `x3` ou `x4`).
- `desc`: Configurações opcionais do jogo ou regras adicionais.

---

## Como Usar

1. Faça o download de todos os arquivos do repositorio e configure seguindo as instruções da sessão anterior.
2. Abra o arquivo `index.html` no navegador. Aperte F11 para habilitar tela cheia. (testado em 1080p)
3. Pressione **Enter** para realizar o sorteio.
4. Após cada partida, registre os resultados clicando no vencedor ou marcando empate.
   - Vitória = 3 pontos
   - Empate = 1 ponto

### Estrutura do Campeonato

- **Rodadas:** O campeonato é dividido em 4 rodadas (atualmente hardcoded).
- **Final Four:** Os 4 melhores avançam para as semifinais e finais:
  - **Semifinais:** Vitória = 12 pontos, Derrota = 6 pontos.
  - **Finais:** Vitória = 24 pontos, Derrota = 12 pontos.

Ao final, o app exibe uma animação de premiação com a classificação final de cada jogador.

---

## Créditos

Músicas e imagens pertencem aos seus respectivos donos e foram obtidas/editadas em pesquisas no Google ou dos jogos homenageados.
Lib Slot Machine: https://github.com/josex2r/jQuery-SlotMachine

**Desenvolvimento:** odelot

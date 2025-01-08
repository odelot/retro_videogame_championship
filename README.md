
# retro_videogame_championship
[![pt-br](https://img.shields.io/badge/lang-pt--br-green.svg)](https://github.com/odelot/retro_videogame_championship/blob/main/README.pt-br.md)

## What is it?

This is a standalone web app (works offline) designed to help retro gaming enthusiasts organize random draws for championships. The app randomly selects consoles, games, and opponents, encouraging players to step out of their comfort zones.

Inspired by the chaotic fun of "Chance Time" from *Mario Party*, the app features a similar draw mechanic: a participant is chosen to spin the wheel and determine the console, number of players, opponents, and the game to be played.

🎥 **Watch the video demo:**

[![Watch the video](https://img.youtube.com/vi/iL1kgRQqBks/hqdefault.jpg)](https://youtube.com/shorts/iL1kgRQqBks)

Enjoyed the idea? Had fun using it? Got suggestions for new features? Consider buying me a beer! 🍺 ^.^

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/odelot)

---

### Disclaimer

This project started as a quick and simple idea for our retro gaming event. Everything — HTML, CSS, and JavaScript — is crammed into a single `index.html` file. It was developed and tested in full screen mode in a 1080p resolution. Many variables and function names are in Portuguese. If you'd like to help improve or translate the code, feel free to submit a pull request. Thanks!

---

## How to Configure

You'll need to edit the JSON lists at the end of the `index.html` file to customize your championship.

### Step 1: Add Players

Replace names and profile images in the `participantes` array:
```javascript
let evento = {    
    participantes: [
      { nome: "Blake Lively", rodada1: 0, total: 0, profileImg: "blake.png" },
      { nome: "Tom Hanks", rodada1: 0, total: 0, profileImg: "tom.png" },
      // Add more players as needed
    ],
    rodadaAtual: 1,
    rodadas: new Array(4),
};
```
Each player needs:
- `nome`: Player name.
- `profileImg`: Image path (recommended size: 195x177px).

### Step 2: Add Consoles

Update the `listaDeVideoGames` array with the consoles for your event:
```javascript
const listaDeVideoGames = [
    { nome: "Dreamcast", imagem: "dreamcast.png" },
    { nome: "GameCube", imagem: "gamecube.png" },
    // Add more consoles as needed
];
```

### Step 3: Add Games

Define the games for each console in the `jogos` array:
```javascript
const jogos = [
    { console: "SNES", estacao: "x2", jogo: "Mario Kart", desc: "" },
    { console: "PS1", estacao: "x2", jogo: "Tekken 3", desc: "Best of 3 rounds." },
    // Add more games as needed
];
```
- `console`: Must match a name in the `listaDeVideoGames`.
- `estacao`: Number of players (`x2`, `x3`, or `x4`).
- `desc`: Optional game settings or additional rules.

---

## How to Use

1. Download all files and configure the web app following the instructions above.
2. Open `index.html` in your browser. Press F11 to enable full-screen setting (tested with 1080p).
3. Press **Enter** to perform the draw.
4. After each match, record the results by clicking on the winner or marking a tie.
   - Win = 3 points
   - Tie = 1 point

### Championship Structure

- **Rounds:** The championship runs for 4 rounds (currently hardcoded).
- **Final Four:** Top 4 players advance to semifinals and finals:
  - **Semifinals:** Win = 12 points, Loss = 6 points.
  - **Finals:** Win = 24 points, Loss = 12 points.

At the end, the app shows an animated awards ceremony highlighting the final standings.

---

## Credits

Music and images belong to their respective owners and were sourced or edited from Google searches or the games being celebrated.
Lib Slot Machine: https://github.com/josex2r/jQuery-SlotMachine

**Development:** odelot

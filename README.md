# 🕹️ FliperamaExpanded

**Transforme o fliperama do Stardrop Saloon em um arcade de verdade no Stardew Valley.**

O mod adiciona uma economia completa de fliperama ao Saloon — **Fichas do Saloon**, **tickets de fidelidade**, **roleta de prêmios** e o **Journey of the Prairie King** integrado — e ainda permite jogar **clássicos retrô** (Game Boy Advance, Super Nintendo, NES, Mega Drive e Game Boy/Color) direto nas máquinas do bar, se você quiser.

---

## 🧩 Do que é feito o mod

O FliperamaExpanded tem **duas partes**:

| Parte | O que faz | Obrigatório? |
| --- | --- | --- |
| **Host** | A economia: fichas, tickets, roleta, HUD, máquinas ligadas pelo Gus, Prairie King pago | ✅ Sim, sempre |
| **Módulos** | Máquinas de jogos retrô (GBA, SNES, NES, Mega Drive, Game Boy) | ⬜ Não, instala só o que quiser |

Os módulos disponíveis:

| Módulo | Joga jogos de | Extensões de arquivo |
| --- | --- | --- |
| `Module.GBA` | Game Boy Advance | `.gba` |
| `Module.SNES` | Super Nintendo | `.sfc`, `.smc` |
| `Module.NES` | NES (Nintendinho) | `.nes` |
| `Module.MegaDrive` | Mega Drive / Genesis | `.md`, `.gen`, `.bin`, `.smd` |
| `Module.GameBoy` | Game Boy e Game Boy Color | `.gb`, `.gbc` |

---

## 📦 Qual pacote baixar?

Tudo fica na raiz deste repositório (e também na aba **Releases**, quando houver). Escolha conforme a sua situação:

### 🆕 Nunca instalei o mod → baixe o **All-in-One**
`FliperamaExpanded-AllInOne-0.2.0.zip` — vem com o host + **todos** os módulos **e as pastas `roms/`, `bios/`, `saves/` já criadas**. É a opção mais fácil: instala uma vez e tem tudo.

### 🧑‍🌾 Vim do Nexus Mods (já tenho o host instalado)
Você já tem o FliperamaExpanded (economia/Prairie King) pelo Nexus. Agora só falta escolher como quer os jogos retrô:

- **Quero tudo, sem complicação** → baixe o **All-in-One** e extraia por cima da pasta antiga (substitui pela versão completa).
- **Quero só alguns consoles** → baixe os **módulos avulsos** de que gostar (ex.: só `FliperamaExpanded.Module.GBA-0.2.0.zip`). Cada módulo se instala sozinho, sem mexer no host.

> 💡 A economia, as fichas e o Prairie King pago funcionam **com ou sem** módulos. Os módulos são um extra à parte.

---

## 🛠️ Instalação (passo a passo)

> Requisitos: **Stardew Valley 1.6+** e **SMAPI 4.0+** (se não tem o SMAPI, instale primeiro — é o "carregador de mods" do jogo).

**1. Encontre a pasta `Mods` do jogo**

No Linux (Steam): `~/.steam/steam/steamapps/common/Stardew Valley/Mods`
No Windows (Steam): `C:\Arquivos de Programas (x86)\Steam\steamapps\common\Stardew Valley\Mods`

**2. Extraia o zip**

O zip já contém a pasta `FliperamaExpanded` (com `dll`, `assets`, `i18n`, `manifest.json` e — no All-in-One — as pastas `roms/`, `bios/`, `saves/` e `modules/` já criadas). No final deve ficar assim:

```text
Mods/
└── FliperamaExpanded/
    ├── FliperamaExpanded.dll       ← o host
    ├── roms/                       ← onde vão seus jogos
    ├── bios/                       ← BIOS opcional
    ├── saves/                      ← saves automáticos
    ├── modules/                    ← só existe se você instalou módulos
    │   ├── gba/
    │   ├── snes/
    │   └── ...
    └── ...
```

> ⚠️ **Linux: evite "pasta com subpasta" (o clássico `FliperamaExpanded/FliperamaExpanded/`).**
> O que acontece: seu gerenciador de arquivos cria uma pasta com o nome do zip ao extrair. Não é bug do mod — é comportamento do Ark/file-roller/nautilus.
>
> **Do jeito certo:** extraia o zip em **qualquer lugar** (ex.: `Downloads`) e depois **mova a pasta `FliperamaExpanded` que aparece para dentro de `Mods/`**.
>
> ```text
> Downloads/FliperamaExpanded-AllInOne-0.2.0/   ← o que o gerenciador cria
> └── FliperamaExpanded/                        ← PASSO ESTA pasta p/ Mods/
> ```
>
> ⚠️ Se você já tinha o FliperamaExpanded instalado (ex.: versão do Nexus), **pode extrair por cima** — os arquivos são substituídos, nada se quebra. No Linux, se o gerenciador reclamar, apague a pasta antiga e extraia a nova no lugar.

**3. Rode o jogo pelo SMAPI**

O mod cria o arquivo `config.json` na primeira execução. Você verá no log do SMAPI quantos módulos foram carregados (ex.: *"5 module(s) loaded"*).

**4. Coloque seus jogos (ROMs)**

As pastas já vêm criadas no All-in-One (ou são criadas sozinhas na primeira execução, se você instalou só o host). É só colocar os arquivos:

```text
Mods/FliperamaExpanded/roms/
├── gba/        ← seus jogos .gba
├── snes/       ← seus jogos .sfc / .smc
├── nes/        ← seus jogos .nes
├── megadrive/  ← seus jogos .md / .gen
└── gameboy/    ← seus jogos .gb / .gbc
```

**5. Jogue!**

Entre no Saloon a partir das **12:00** (o Gus liga as máquinas uma a uma) e interaja com uma máquina. **Compre fichas no balcão do Gus** (100 fichas por 1.000 ouros) e aproveite.

---

## 🎮 Primeira vez jogando — o que esperar

- As máquinas começam o dia **desligadas**; o Gus liga cada uma a partir das **12:00** e desliga tudo às **23:00** (sim, ele encerra sua sessão com um aviso educado se você ainda estiver jogando 😅).
- Cada partida cobra **fichas**: na entrada e por hora do relógio do jogo (padrões: 10 + 10/hora, configurável).
- Jogue **5 horas contínuas** e ganhe 1 **Ticket do Fliperama** — troque na **Roleta de Prêmios** do Gus.
- Abigail, Sam, Sebastian e Shane ocupam as máquinas em dias de chuva e sextas à noite — respeite a vez deles!

### Controles rápidos

| Ação | Tecla |
| --- | --- |
| Pausa | `F1` |
| Salvar estado / Carregar estado | `F5` / `F8` |
| Turbo 3× | `Espaço` (ou gatilho direito do gamepad) |
| Sair da máquina | `Esc` |

---

## ❓ Perguntas frequentes

**De onde consigo os jogos (ROMs)?**
Use apenas **ROMs homebrew** (criadas por fãs, com licença livre) ou **backups dos seus próprios cartuchos**. Este projeto **não distribui nem hospeda ROMs comerciais** — por lei, você só pode ter ROMs de jogos que você possui.

**Preciso da BIOS do Game Boy Advance?**
**Não.** O emulador funciona sem ela (modo HLE). Se você tem a BIOS (dump do seu próprio hardware), coloque em `bios/gba/gba_bios.bin` para jogos com inicialização idêntica ao hardware — mas é opcional.
**Funciona no Windows?**

**Sim.** Cada módulo traz os dois núcleos nativos: `.so` (Linux) e `.dll` (Windows x64) — o mod escolhe o correto automaticamente. Testado no Windows e Linux (x64).

**Funciona no macOS?**

Ainda não — os núcleos macOS (`.dylib`) serão acompanhados aqui quando disponíveis.

**Funciona em multiplayer?**
Sim — single-player e multiplayer (host e farmhands), com uma pessoa por máquina de cada vez.

**Como desinstalo?**
Basta remover a pasta `Mods/FliperamaExpanded/`. O mod não altera nenhum arquivo do jogo.

---

## ⚙️ Configuração (avançado)

O `config.json` é criado na primeira execução dentro da pasta do mod. Principais opções:

| Opção | Padrão | O que faz |
| --- | --- | --- |
| `TokenBundleAmount` / `TokenBundlePrice` | `100` / `1000` | Tamanho e preço do pacote de fichas |
| `SessionStartTokenCost` | `10` | Fichas cobradas para iniciar a partida |
| `HourlyTokenCost` | `10` | Fichas por hora do relógio do jogo |
| `HoursPerPrizeTicket` | `5` | Horas de jogo para ganhar 1 ticket |
| `Key*` | — | Mapeamento de teclado (dá pra remapear pelo menu do fliperama!) |

---

## 🔨 Nota para desenvolvedores

Este repositório distribui **apenas os pacotes de release (binários)** — o código-fonte não está publicado aqui.

Se você é desenvolvedor:

- Alvo: .NET 6 (`net6.0`), SMAPI 4.5.2, Stardew Valley 1.6.15 (testado no Linux).
- Os núcleos nativos são Libretro — **Windows**: `_libretro.dll` (mGBA, Snes9x, FCEUmm, Genesis Plus GX, Gambatte) e **Linux**: `_libretro.so` (mesmos núcleos).
- Reprodução dos pacotes: `dotnet build` + script de empacotamento geram exatamente os zips da raiz deste repositório.

---

## 📜 Licenças

| Componente | Licença |
| --- | --- |
| Host (este repositório) | [MIT](LICENSE) |
| 0Harmony (integração) | MIT |
| mGBA (GBA) | MPL 2.0 |
| Snes9x (SNES) | Snes9x Non-Commercial |
| FCEUmm (NES) | GPL 2.0 |
| Genesis Plus GX (Mega Drive) | Non-Commercial |
| Gambatte (Game Boy/Color) | GPL 2.0 |

Cada módulo carrega sua licença completa dentro da própria pasta (`modules/{console}/licenses/`).

---

## ❤️ Créditos

**Autor:** alichan (tsubasachan)
**Nexus Mods:** [FliperamaExpanded](https://www.nexusmods.com/stardewvalley/mods/52497) — lá você encontra só o host; os módulos e o pacote completo estão aqui.
**Jogo:** Stardew Valley, da ConcernedApe.
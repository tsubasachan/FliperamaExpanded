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

## 📦 Como instalar

> Requisitos: **Stardew Valley 1.6+** e **SMAPI 4.0+** (se não tem o SMAPI, instale primeiro — é o "carregador de mods" do jogo).

### ✅ Jeito recomendado: use o instalador

Baixe o instalador da sua plataforma (arquivos na raiz deste repositório) e execute:

| Plataforma | Arquivo |
| --- | --- |
| Windows | `FliperamaExpanded.Installer-win-x64.zip` |
| Linux | `FliperamaExpanded.Installer-linux-x64.zip` |

Após baixar, **extraia o zip** em uma pasta qualquer e abra o instalador que está dentro (`FliperamaExpanded.Installer.exe` no Windows ou `FliperamaExpanded.Installer` no Linux). No Linux, dê permissão de execução antes:

```bash
chmod +x FliperamaExpanded.Installer
./FliperamaExpanded.Installer
```

O instalador faz tudo sozinho:

1. **Encontra o Stardew Valley** (Steam/GOG) — ou você informa a pasta;
2. mostra os consoles e você **escolhe só os que quiser**;
3. **baixa os módulos direto deste repositório**, confere a **integridade (SHA-256)** e instala no lugar certo;
4. cria as pastas `roms/`, `bios/` e `saves/` dos consoles escolhidos (sem mexer em nada que já exista).

> 💡 O instalador baixa somente o binário **da sua plataforma** — nunca mistura Linux e Windows.

### 🧰 Instalação manual (zips)

Se preferir na mão, use os pacotes da raiz deste repositório. **Escolha sempre o pacote da sua plataforma** (`-win-x64` ou `-linux-x64`):

| Situação | Pacote |
| --- | --- |
| Primeira vez, quero tudo | `FliperamaExpanded-AllInOne-<plat>-0.2.0.zip` |
| Já tenho o host (ex.: Nexus) e quero um console | `FliperamaExpanded.Module.<Console>-<plat>-0.2.0.zip` |
| Só o host | `FliperamaExpanded-0.2.0.zip` |

> ⚠️ Os pacotes são separados **por plataforma de propósito**: um zip nunca mistura `.so` (Linux) com `.dll` (Windows).

---

## 🛠️ Instalação manual, passo a passo

**1. Extraia o zip**

O zip contém a pasta `FliperamaExpanded` (com `dll`, `assets`, `i18n`, `manifest.json` e, nos módulos, `modules/{console}/`). O resultado final:

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
> Seu gerenciador de arquivos cria uma pasta com o nome do zip ao extrair. Não é bug do mod — é comportamento do Ark/file-roller/nautilus.
>
> **Do jeito certo:** extraia o zip em **qualquer lugar** (ex.: `Downloads`) e depois **mova a pasta `FliperamaExpanded` que aparece para dentro de `Mods/`**.
>
> ```text
> Downloads/FliperamaExpanded-AllInOne-linux-x64-0.2.0/   ← o que o gerenciador cria
> └── FliperamaExpanded/                                  ← PASSO ESTA pasta p/ Mods/
> ```
>
> ⚠️ Se você já tinha o FliperamaExpanded instalado (ex.: versão do Nexus), **pode extrair por cima** — os arquivos são substituídos, nada se quebra.

**2. Rode o jogo pelo SMAPI**

O mod cria o arquivo `config.json` na primeira execução. Você verá no log do SMAPI quantos módulos foram carregados (ex.: *"5 module(s) loaded"*).

**3. Coloque seus jogos (ROMs)**

As pastas já vêm criadas no All-in-One / pelo instalador (ou são criadas sozinhas na primeira execução, se você instalou só o host). É só colocar os arquivos:

```text
Mods/FliperamaExpanded/roms/
├── gba/        ← seus jogos .gba
├── snes/       ← seus jogos .sfc / .smc
├── nes/        ← seus jogos .nes
├── megadrive/  ← seus jogos .md / .gen
└── gameboy/    ← seus jogos .gb / .gbc
```

**4. Jogue!**

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

**Sim.** No Windows use os pacotes `-win-x64` (ou o instalador `FliperamaExpanded.Installer.exe`) e no Linux os `-linux-x64`. Os núcleos nativos (`.dll`/`.so`) vêm separados por plataforma, então nunca há mistura. Testado no Windows e Linux (x64).

**Funciona no macOS?**

Ainda não — os núcleos macOS (`.dylib`) serão acompanhados aqui quando disponíveis.

**Funciona em multiplayer?**
Sim — single-player e multiplayer (host e farmhands), com uma pessoa por máquina de cada vez.

**Como atualizo para uma versão nova?**
Rode o instalador de novo (ele baixa a versão mais recente) ou extraia o zip novo por cima. Suas ROMs e saves ficam intactos.

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
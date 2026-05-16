# First Cut

Análise automática de takes de vídeo para edição. App para macOS que lê seus brutos, identifica takes utilizáveis vs descartáveis, gera relatório HTML, e exporta projeto pronto para Final Cut Pro / DaVinci Resolve.

## O que faz

Você joga uma pasta com 50 vídeos. O First Cut:

1. **Detecta cortes** dentro de cada vídeo (cada vez que você parou e voltou)
2. **Analisa cada take** — sharpness, estabilidade de câmera, exposição, áudio
3. **Classifica** em Good / Usable / Problematic / Duplicate
4. **Exporta** os takes selecionados + projeto FCPXML + EDL + relatório HTML

Em vez de assistir 2 horas de bruto pra escolher takes, você abre o relatório e clica nos bons.

## Download

Última versão: [Releases](https://github.com/lucasbumbo/firstcut/releases/latest)

Baixe `FirstCut_beta.zip`, descompacte, arraste `First Cut.app` pra Aplicativos.

## Auto-update

O app verifica atualizações ao abrir. Quando uma nova versão sai aqui, ele te oferece atualizar na próxima inicialização.

## Como usar

1. Abra o app — uma janela do browser abre automaticamente
2. Arraste seus vídeos (ou pasta inteira) na área de drop
3. Escolha o modo (A-Roll / B-Roll / Auto)
4. Clique **Analisar**
5. Quando terminar, clique **Abrir no Final Cut** ou **DaVinci**

Outputs ficam em `~/Documents/First Cut/` por padrão (configurável no app).

## Requisitos

- macOS 12+
- Python 3 (vem com o Xcode Command Line Tools)
- Homebrew + ffmpeg (instalados automaticamente na primeira execução)

## Troubleshooting

**App não abre:** abra o Terminal, navegue até a pasta, rode `./First Cut.app/Contents/MacOS/First Cut` pra ver o erro real.

**"No space left on device":** sua pasta de outputs está cheia. No app, clique **Limpar exports** ou aponte pra outra pasta com **Trocar pasta**.

**Análise muito lenta:** vídeos 4K em hardware antigo são CPU-limited. O app usa ffmpeg com hardware decode (VideoToolbox) — verifique se seu Mac tem chip Apple Silicon ou GPU dedicada.

**Takes errados sendo exportados:** abra uma issue com o vídeo + screenshot do relatório. Os critérios estão em desenvolvimento ativo.

## Licença

Beta privado — ainda sem licença pública. Não redistribuir.

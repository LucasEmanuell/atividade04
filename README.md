# Eixos 3D em RA: Visualizador de Sistema de Coordenadas

Aplicação WebAR (A-Frame + AR.js) que sobrepõe um sistema de eixos
ortogonais X/Y/Z sobre um marker Hiro, voltada ao ensino de Geometria
Analítica e Álgebra Linear.

**Autor:** Lucas Emanuel Rodrigues de Matos

## Como usar

1. Acesse o link público no Netlify pelo celular (HTTPS obrigatório).
2. Permita o acesso à câmera quando solicitado.
3. Imprima ou exiba o marker Hiro:
   https://raw.githubusercontent.com/AR-js-org/AR.js/master/data/images/hiro.png
4. Aponte a câmera para o marker.

## Interações

| Gesto | Efeito |
|---|---|
| Toque rápido na tela | Gera o vetor `v = (2, 1, 1)` com animação (toque de novo para remover) |
| Pressionar e segurar | Amplia os eixos em 1,5× para inspecionar (solta para voltar ao tamanho normal) |

## Stack

- [A-Frame 1.4.2](https://aframe.io) (MIT License)
- [AR.js 3.4.5](https://ar-js-org.github.io/AR.js-Docs/) (MIT License)

## Decisão de design: primitivas em vez de modelo 3D externo

Os eixos e o vetor foram feitos só com primitivas do A-Frame
(`a-cylinder`, `a-cone`, `a-sphere`), sem nenhum arquivo `.glb`/`.obj`
externo. A ideia veio de um exemplo do material do curso, em que um
modelo 3D complexo é trocado por primitivas pra deixar a cena mais
leve.

Vantagens:
- Carrega rápido, sem precisar baixar nenhum asset externo.
- Cada eixo fica exatamente na cor e proporção que eu quis (X
  vermelho, Y verde, Z azul), seguindo a convenção de Geometria
  Analítica.
- Sem textura e com geometria simples, os pontos de otimização do
  curso (polígonos, texturas, draw calls) já ficam baixos desde o
  começo.

Mais detalhes em [`LEIA-ME.txt`](./LEIA-ME.txt).

# Simulação de Movimento Browniano

Simulação interativa do movimento browniano feita com HTML, Canvas e JavaScript. Uma partícula grande (o "pólen", em amarelo) fica imersa num fluido de milhares de partículas pequenas (as moléculas de "água"). A agitação térmica das moléculas faz o pólen se mover de forma irregular, e a sua trajetória é desenhada em vermelho.

🔗 **Acesse a simulação:** https://augusto-schf.github.io/movimento_browniano/

## Contexto acadêmico

Este trabalho foi desenvolvido para a disciplina de **Desenvolvimento de Narrativas Textuais**, sob orientação da **Profa. Dra. Cilene Rodrigues**, no **IMPA Tech**, no Rio de Janeiro, em 2026.

A simulação ilustra o fenômeno estudado nos trabalhos de Albert Einstein (1905) e Jean Perrin (1908–1909). Esses trabalhos mostraram que o movimento errático de partículas suspensas em um líquido é causado pelos choques com as moléculas do fluido, o que deu evidência experimental da existência de átomos e moléculas.

## Como usar

Basta abrir o link acima. Também dá para baixar o arquivo `index.html` e abri-lo em qualquer navegador, sem instalar nada.

| Controle | Função |
|---|---|
| **Pausar / Continuar** | Pausa ou retoma a simulação |
| **Reiniciar** | Gera novas moléculas com velocidades aleatórias e recoloca o pólen no centro |
| **Esconder / Mostrar água** | Oculta as moléculas de água na tela, que continuam se movendo e colidindo com o pólen |
| **Passos por quadro** | Quantos passos de simulação são calculados a cada quadro da tela, o que acelera ou desacelera o tempo |

A simulação termina sozinha quando o pólen chega perto de uma das bordas.

## Modelo físico

- **Moléculas de água:** cerca de 4.600 partículas de raio 1 e massa 2, dispostas inicialmente numa grade. Cada componente da velocidade é sorteado de uma distribuição normal com desvio padrão $\sigma = \sqrt{kT/m}$, como na distribuição de Maxwell–Boltzmann.
- **Pólen:** uma partícula de raio 15 e massa 50, que começa no centro da tela.
- **Colisões:** elásticas, ou seja, com conservação de momento e energia cinética, calculadas entre o pólen e cada molécula. Para simplificar, as moléculas de água não colidem entre si.
- **Paredes:** as partículas são refletidas ao atingir as bordas.
- **Integração:** método de Euler explícito com passo $\Delta t = 1/300$.
- **Linha roxa:** mostra o deslocamento horizontal do pólen em relação ao centro.

## Arquivos

- `index.html`: toda a simulação (HTML, CSS e JavaScript) num único arquivo.

A versão original foi escrita em Python com Pygame e depois convertida para JavaScript, para rodar direto no navegador.

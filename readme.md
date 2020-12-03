# Análise superficial da página inicial do portal globo.com através da ferramenta GoogleLighthouse

A intenção dessa análise é, apenas, avaliar de forma superficioal o comportamento da página web para detectar falhas ou acertos sobre sua construção e avaliar.

### O resultado da análise pode ser visualizado por completo [neste link](https://nicacioliveira.github.io/avaliacao-arquitetural-arqsoft-20203/relatorio-globo.com.html)


## Roteiro:
- Análise de performance
- Análise de acessibilidade
- Análise de boas práticas
- Análise de SEO
- Conclusão/Comentários

---

<div style="display: flex;">
    <img style="margin: 0 auto;" src="images/performance.png"/>
</div>

# Avaliação sobre o carregamento da página.

Nessa avaliação, observei que mesmo que o software rode mais algumas vezes a performance não varia mais que a média de 6s para que a página carregue por completo. Do ponto de vista do usuário, 6 segundos é um tempo alto, porém existem ressalvas sobre essa avaliação feita pela ferramenta.

A principal avaliação aqui está em identificar o tamanho dos arquivos, a minificação de scripts, o uso de arquivos estáticos (imagens, css etc), o tamanho da página em relação a quantidade de elementos, o bloquei do dom para carregamento e o tempo de renderização da primeira parte visual da tela.

## Problemas

Os principais problemas encontrados aqui estão relacionados ao uso de javascript excessivo, ou seja, que não será utilizado, levando a perda de mais de 1s no carregamento. O uso de não estaticos que poderiam estar em algum servidor de estáticos mas estão vindo direto do servidor da própria aplicação em diversos locais e o uso excessivo de scripts de terceiros.

## Acertos

O uso correto do javascript e o tamanho correto das imagens de acordo com aquilo que é visto são os pontos mais fortes e que contribuem para o carregamento rápido da página


## Considerações

É importante entender que esse número aparentemente baixo da avaliação de performance pode não representar a realidade em outros browsers e clientes. Também é importante lembrar que os requisitos para a visualização da página podem exigir que o carregamento aconteça da forma citada para que o conteúdo seja avisualmente agradável e útil para o usuário final.

Outro ponto que gostaria de destacar é que essa análise é sempre um pouco confusa. Por um lado fala sobre o uso indevido de muitas linhas de código de javascrit para montar a página e por outro fala de um "uso correto" do mesmo o que torna a análise através da ferramenta um pouco confusa.


---

<div style="display: flex;">
    <img style="margin: 0 auto;" src="images/accessibility.png"/>
</div>

# Avaliação sobre acessibilidade da página

O Lighthouse avalia acessibilidade em relação ao uso de cores muito distintas, claras ou escuras demais, sequência de tags html, nomes, títulos e rótulos em tags que são utilizados para suprir acessibilidade em sites etc.

Por exemplo, o uso de rótulos com a descrição do que uma imagem significa é importante para a acessibilidade do site no sentido de indicar o que aquela imagem está querendo "dizer".

## Problemas

Basicamente cores muito claras o que prejudica a navegação para algumas pessoas e elementos sem título ou rótulo.

## Acertos

Atributos com "aria" do html bem utilizados, botões e links com nomes acessíveis e discerníveis etc. 

## Considerações

Em acessibilidade o site está dentro de um nível aceitável de acordo com a ferramenta, com poucos problemas estruturais do ponto de vista da marcação da página. Essa análise nos ajuda a entender se temos uma página que está dentro do esperado no que se diz respeito a acessibilidade em um website.

---

<div style="display: flex;">
    <img style="margin: 0 auto;" src="images/best_practices.png"/>
</div>

# Avaliação sobre boas práticas na construção da página

Em boas práticas a ferramenta verifica se a página está seguindo boas práticas de padrões web. Por exemplo, uso de https, erros no console, requisições para APIs obsoletas, proporções corretas em imagens etc.

Abaixo alguns pontos sobre o resultado

## Problemas

Foram encontradas algumas requisições para serviços que não utilizam https e isso é considerado um problema do ponto de vista da proteção dos dados que estão sendo enviados por essas requisições.

Segundo o lighthouse, os scripts de aviso sobre o uso de cookies do portal, podem conter problemas relacionados a origem cruzada.

Também foi percebido que o portal utiliza um aversão muito antiga do JQuery o que pode ser uma falha do ponto de vista de que a biblioteca pode conter falhas de segurança por estar em uma versão antiga.

## Acertos

Todoas as imagens do portal foram cuidadosamente dimensionadas, o html possui a marcação esperada pelos padrões aceitos na web, evita cache de aplicativo etc.

## Considerações

Um ponto interessante dessa análise é que o lighthouse indicou o uso de uma versão obsoleta do JQuery mas ao mesmo tempo indica que o site possui como ponto positivo o não uso de bibliotecas obsoletas deixando a análise um pouco confusa.

Esse ponto de análise ajuda a identificar se estamos esquecendo código morto na página, como importações de scripts que não são úteis, por exemplo.

---

<div style="display: flex;">
    <img style="margin: 0 auto;" src="images/seo.png"/>
</div>

# Avaliação sobre SEO

Aqui ocorre uma verificação sobre se a página está otimizada para que robos de mecanismos de buscas consigam indexar o conteúdo sem maiores problemas.

## Problemas

Praticamente nenhum ponto ruim nesse caso. Apenas um alerta sobre botões e links e seus tamanhos, porém, nada grave que diminua a nota nesse ponto.

## Acertos

Todas as tags necessárias para robos estão certas. O uso de um arquivo robots.txt também está válido, o que faz com que a página indique o que um robô indexador pode ou não pode fazer no site. Fontes totalmente legíveis para esse aspecto e o html evita plugins.

## Considerações

Talvez esse ponto seja o mais importante em relação a o que espera-se da ferramenta. Páginas web, em sua maioria dependem de que a indexação de mecanismos de busca seja eficiente e ajude a expor o site o máximo possível na internet. Então, em geral, é interessante levar em conta como principal ponto a análise de SEO da página e sempre tentar adapta-la para alcançar a maior pontuação possível nesse aspecto.

---

# -> Conclusão

A ferramenta em si é um excelente suporte para que uma página ou páginas web sejam avaliadas do ponto de vista do que espera-se ou o mínimo que espera-se para que elas funcionem bem no browser do cliente. Porém, o seu uso deve ser feito com cautela. A ferramente poderia receber inputs, por exemplo, para que o desenvolvedor pudesse indicar explicitamente que ele entender que está utilizando chamadas para uma api que não possui https para que isso não afete a análise final.

Outro ponto é que qualquer um dos quatro pontos são subjetivos de certa forma. Por exemplo, para atingir a pontuação máxima para os quatro pontos a página teria que ter praticamente uma estrutura básica sem nada muito requintado, quase como uma página em branco. Isso torna-se um problema do ponto de vista de que quanto mais o desenvolvedor adapta a página para uma melhor usabilidade do cliente, mais a página fica complexa e com muitos elementos e isso diminui a sua nota em todos esses pontos e por esse motivo digo que a análise desses pontos é muitas vezes subjetiva no sentido de estar ligada ao conforto do usuário.

Novamente, sinto falta de um input para indicar sobre o que eu estou ciente na página para a ferramenta para que ela ignore determinados pontos em sua análise.
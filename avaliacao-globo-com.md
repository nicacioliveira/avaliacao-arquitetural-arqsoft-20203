Análise superficial do globo.com através da ferramenta GoogleLighthouse

<i>imagem</i>

Ao ralizar uma avaliação simples através do google lighthouse, vamos pontuar algumas observações sobre os resultados.

<i>imagem do carregamento de pagina</i>

Avaliação de carregamento da página.

Nessa avaliação, observei que mesmo que o software rode mais algumas vezes a performance não varia mais que a média de 6s para que a página carregue por completo. Do ponto de vista do usuário, 6 segundos é um tempo alto, porém existem ressalvas sobre essa avaliação feita pela ferramenta.

A principal avaliação aqui está em identificar o tamanho dos arquivos, a minificação de scripts, o uso de arquivos estáticos (imagens, css etc), o tamanho da página em relação a quantidade de elementos, o bloquei do dom para carregamento e o tempo de renderização da primeira parte visual da tela.

Problemas

Os principais problemas encontrados aqui estão relacionados ao uso de javascript excessivo, ou seja, que não será utilizado, levando a perda de mais de 1s no carregamento. O uso de não estaticos que poderiam estar em algum servidor de estáticos mas estão vindo direto do servidor da própria aplicação em diversos locais e o uso excessivo de scripts de terceiros.

Acertos

O uso correto do javascript e o tamanho correto das imagens de acordo com aquilo que é visto são os pontos mais fortes e que contribuem para o carregamento rápido da página


Considerações

É importante entender que esse número aparentemente baixo da avaliação de performance pode não representar a realidade em outros browsers e clientes. Também é importante lembrar que os requisitos para a visualização da página podem exigir que o carregamento aconteça da forma citada para que o conteúdo sej avisualmente agradável e útil para o usuário final



<i>imagem da acessibilidade de pagina</i>

Avaliação sobre acessibilidade do site



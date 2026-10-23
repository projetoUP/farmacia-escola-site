# Farmácia-Escola — site educacional

## Como abrir
- Abra `index.html` no navegador para testar a página.
- Para publicar, envie `index.html` e a pasta `assets/` para a raiz do repositório GitHub Pages.

## Novidades desta versão
- Carrossel horizontal de fotos do projeto na página inicial; imagens mantidas na proporção original (contain) com fundo preto nas faixas vazias.
- Passaporte do visitante com progresso salvo no navegador.
- Visita guiada que percorre as seções.
- Glossário com busca.
- Blocos “Explorar as informações” nos cartões de medicamentos.
- Desafio de descarte correto na seção Sustentabilidade.
- Navegação ativa, entradas suaves e animações que respeitam o modo de redução de movimento.
- Na seção Vivências, removidas as molduras/quadrados animados; adicionado controle funcional entre as três fases.
- A expansão das imagens é inicializada depois que os cartões de medicamentos são renderizados.

## Medicamentos
As fotos dos produtos são referências visuais externas. Se um endereço remoto falhar, o cartão usa uma ilustração local para não ficar vazio. Concentração, forma e volume variam por fabricante; o site é educativo, não orienta automedicação e não substitui bula ou profissional de saúde.

## Dependências
A cena tridimensional da seção Consulte usa Three.js carregado por CDN. Para essa parte funcionar, o navegador precisa ter acesso à internet. As demais seções usam HTML, CSS e JavaScript.


## Referências de apresentação consultadas
- Reactine 10 mg: Kenvue Brasil — https://www.kenvuebrands.com/br/reactine/antialergico-reactine
- Ibuprofeno gotas 100 mg/mL: Extrafarma — https://www.extrafarma.com.br/ibuprofeno-100mg-gotas-20ml-generico-neoquimica/p
- Dexclorfeniramina solução oral 0,4 mg/mL: Pague Menos — https://www.paguemenos.com.br/maleato-de-dexclorfeniramina-0-4mg-solucao-oral-100ml-generico-prati-donaduzzi/p
- Cefalexina suspensão 250 mg/5 mL: ABL Brasil — https://www.ablbrasil.com.br/cefalexina-monoidratada-suspensao/

## Ícone da aba
O favicon local está em `assets/favicon.svg`, com alternativas PNG/ICO. É um quadrado branco com uma cruz vermelha central.

## Imagens dos medicamentos
Os cartões priorizam fotografias de embalagens comerciais em fontes de farmácias. Se uma imagem primária falhar, o site tenta uma segunda foto real quando disponível; se ambas falharem, informa que a foto está temporariamente indisponível e não cria uma embalagem ilustrada fictícia.

## Revisão de imagens, galeria e glossário (23/10/2026)
- A galeria inicial percorre as 22 fotos em loop contínuo, com avanço/retorno por setas, teclado e arraste.
- As fotos da equipe usam `object-fit: contain` e fundo preto para manter a proporção sem esticar ou cortar o conteúdo.
- A lista de Aprenda contém 32 medicamentos. As fontes de imagem foram revisadas e várias URLs foram trocadas por imagens de embalagens publicadas em catálogos de farmácias. Em caso de falha, o código tenta uma foto alternativa real quando disponível; se nenhuma carregar, mostra um aviso em vez de desenhar uma embalagem fictícia.
- O glossário foi ampliado para 42 termos com explicações mais detalhadas.
- O ícone da aba do navegador está em `assets/favicon.svg`, com versões alternativas `assets/favicon.png` e `assets/favicon.ico`: fundo branco quadrado e cruz vermelha central.

**Nota sobre imagens externas:** as fotografias dos medicamentos usam endereços de catálogos online e, portanto, precisam de conexão com a internet para carregar. O restante do site continua organizado como uma página estática para GitHub Pages.

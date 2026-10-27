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
As fotos dos produtos são referências visuais externas. O cartão tenta a imagem principal e, quando cadastrada, uma segunda fotografia real. Se nenhuma carregar, mostra um aviso de indisponibilidade — não cria uma embalagem fictícia. Concentração, forma e volume variam por fabricante; o site é educativo, não orienta automedicação e não substitui bula ou profissional de saúde.

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
- A lista de Aprenda contém 38 fichas visuais: 32 medicamentos originais mais 6 produtos distintos adicionados. A azitromicina já existia e foi atualizada, sem duplicação. Inclui filtros Uso único e Suplementos; o cartão de vitamina B12 identifica explicitamente o produto como suplemento alimentar, não medicamento. As fontes de imagem são páginas de catálogos de farmácias. Em caso de falha, o código tenta uma foto alternativa real quando disponível; se nenhuma carregar, mostra um aviso em vez de desenhar uma embalagem fictícia.
- O glossário foi ampliado para 42 termos com explicações mais detalhadas.
- O ícone da aba do navegador está em `assets/favicon.svg`, com versões alternativas `assets/favicon.png` e `assets/favicon.ico`: fundo branco quadrado e cruz vermelha central.

**Nota sobre imagens externas:** as fotografias dos medicamentos usam endereços de catálogos online e, portanto, precisam de conexão com a internet para carregar. O restante do site continua organizado como uma página estática para GitHub Pages.


## Correção da etapa Armazenamento (23/10/2026)
- A etapa **Encaminhamento** agora usa a foto local `assets/rotina_04.jpg`, que corresponde à conversa com um profissional.
- A etapa **Organização** usa uma fotografia real de armazenamento farmacêutico de Abdul Batin, publicada no Pexels: https://www.pexels.com/photo/professional-pharmacist-in-modern-drugstore-space-for-text-13119976/. A página identifica a foto como gratuita sob a licença Pexels. A imagem é carregada diretamente da CDN do Pexels; requer internet.
- Se a fotografia externa não carregar, o site informa isso e utiliza temporariamente `assets/rotina_05.jpg` como imagem ilustrativa local. A interface explicita quando está usando essa alternativa.
- A etapa **Conservação e localização** permanece com imagem ilustrativa local e recebeu texto que explica controle de validade e condições de conservação sem presumir que todo medicamento deve ser refrigerado.

## Feedback via Google Forms (23/10/2026)
- A seção Feedback incorpora o formulário publicado da equipe por meio de um `iframe` e mantém um botão para abri-lo em uma nova aba.
- Respostas enviadas pelo formulário embutido são registradas no Google Forms associado ao link configurado em `index.html`.
- O formulário local original continua disponível no painel recolhível “Usar o formulário local de alternativa”. Ele guarda respostas apenas no navegador/dispositivo e não envia dados à equipe.
- O quiz e o histórico local foram preservados. A versão atual também encaminha o resumo da tentativa ao Google Planilhas por Apps Script, conforme a seção “Histórico online do quiz” abaixo.
- Se o formulário incorporado não aparecer ou pedir acesso, confirme que ele está publicado para participantes com o link. Também é possível usar o botão “Abrir formulário em nova aba”.


## Histórico online do quiz (24/10/2026)
- Ao concluir as 20 perguntas, o site continua salvando a tentativa no histórico local do navegador e também encaminha o resumo ao Google Apps Script publicado pela equipe.
- O envio utiliza o endpoint `/exec` configurado em `index.html`, por meio de uma requisição `POST` com o campo `payload` em formato `application/x-www-form-urlencoded`, compatível com `e.parameter.payload` no Apps Script.
- A planilha registra data/hora, nome do participante, acertos, total de perguntas e aproveitamento. O histórico local segue independente por navegador; a planilha é o histórico central entre visitantes.
- Por segurança e privacidade, o site envia apenas os dados necessários ao resumo e 20 marcadores de acerto/erro para cumprir a validação do serviço. As alternativas selecionadas não são guardadas na planilha.
- Como o endpoint é público e a requisição usa `no-cors`, o navegador não permite ler a confirmação do Apps Script. A interface informa que o envio foi encaminhado e orienta conferir a planilha. Se houver falha de rede, oferece uma tentativa de reenvio.
- Após publicar uma nova versão, faça um teste real: conclua uma tentativa no site, verifique se apareceu uma nova linha na aba `Histórico do Quiz` e apague os registros de teste, se houver. Se não aparecer, confira se o Apps Script está implantado como aplicativo da Web, executa como o proprietário e permite acesso aos visitantes; depois atualize a implantação existente para usar a versão atual do código.
- O endpoint publicado é acessível publicamente. Não use o formulário para dados sensíveis; como qualquer serviço público, pode receber envios falsos. A validação atual limita a estrutura e a pontuação, mas não autentica a identidade do participante.

## Correção do loop da galeria (24/10/2026)
- Ajustado o limite de normalização no sentido horário do carrossel. O ponto anterior fazia a rolagem reiniciar cedo demais por causa do `scroll-snap`, podendo devolver o visitante à foto 22 em vez de chegar à foto 1.
- As setas, o arraste e a navegação por teclado continuam usando o mesmo carrossel de 22 fotos, com imagens inteiras e fundo preto quando sobra espaço.


## Atualização do catálogo visual (27/10/2026)
- Foram adicionados Varylift (diosmina + hesperidina), Vitamina B12 Maxinutri (identificada como suplemento alimentar), espironolactona, alopurinol, hemifumarato de bisoprolol e flutamida. A azitromicina já constava na lista e teve a imagem e a apresentação de referência revisadas para não duplicar o medicamento.
- As fotos enviadas em WhatsApp não foram usadas no catálogo. As imagens são fotografias de embalagens em páginas de catálogos de fabricantes/distribuidores/farmácias e permanecem carregadas de suas fontes originais; precisam de conexão com a internet. Cada card tenta uma segunda foto real quando existe uma alternativa adequada e, se ambas falharem, mostra aviso de indisponibilidade em vez de uma imagem inventada.
- Referências comerciais consultadas para imagens e apresentações: [Neo Química — paracetamol](https://www.neoquimica.com.br/genericos/paracetamol), [Drogaria Nova Esperança — ibuprofeno gotas](https://www.drogarianovaesperanca.com.br/ibuprofeno-gotas-100mg-com-20ml-28654/), [Farmelhor — naproxeno sódico 550 mg](https://www.farmelhor.com.br/naproxeno-sodico-neo-quimica-550mg-caixa-com-20-comprimidos-revestidos-p48640-p892), [Drogaria Minas Brasil — dexclorfeniramina solução oral](https://www.drogariaminasbrasil.com.br/maleato-de-dexclorfeniramina-0-4mg-ml-com-100ml-prati-donaduzzi), [Mevo Farma — clotrimazol creme 10 mg/g](https://www.mevofarma.com.br/clotrimazol-10mg-g-creme-dermatologico---bisnaga-com-20-g-77/p), [Farmafy — nistatina suspensão oral 100.000 UI/mL](https://farmafy.com.br/p/834/nistatina-suspensao-50ml-generico), [Farma22 — fexofenadina 120 mg](https://www.farma22.com.br/cloridrato-de-fexofenadina-120mg-10-comprimidos-revestidos-generico-neo-quimica-1/p), [Norte Sul Real — cefalexina 250 mg/5 mL](https://www.nortesulreal.com.br/p/medicamentos/cefalexina-250mg-100ml-susp/NSM_78544), [Zilfarma — amoxicilina 500 mg](https://portal.zilfarma.com/antibioticos/amoxicilina-500mg-21caps-5689), [Zilfarma — aciclovir 200 mg](https://portal.zilfarma.com/4573-thickbox_default/aciclovir-200mg-30comp60.webp), [RioMed — metformina 850 mg](https://portal.riomeddistribuicao.com.br/genericos/metformina-850mg-30com-geolab-13782), [Drogasil — vitamina B12 Maxinutri](https://www.drogasil.com.br/vitamina-b-12-metilcobalamina-mastigavel-60-comprimidos-maxinutri-1204721.html), [Santa Lucia — espironolactona 25 mg](https://www.santaluciadrogarias.com.br/espironolactona---25mg-30-cprs---germ--g-/p), [Santa Lucia — alopurinol 300 mg](https://www.santaluciadrogarias.com.br/alopurinol-300mg-30-cprs---prat-g-/p), [Oeste Pharma — bisoprolol 5 mg](https://oestepharma.com.br/produtos.php?pagina=241), [NeyFarma — Varylift 450 mg + 50 mg](https://neyfarma.com.br/varylift-uniao-quimica-450mgmais50mg-30-comprimidos/18279-01), [Drogaria Rosário — flutamida 250 mg](https://www.drogariarosario.com.br/g-flutamida-250mg-20cpr-blau/p).
- “Uso único” é um filtro educativo ligado ao exemplo de fluconazol 150 mg em embalagem com uma cápsula. A nota do site esclarece que uma embalagem de uma unidade não determina, por si só, o esquema de tratamento; isso depende da indicação e de orientação profissional.
- O item de vitamina B12 é um suplemento alimentar conforme o rótulo da fonte, por isso foi separado no filtro “Suplementos” e não classificado como medicamento.
- As fontes externas podem mudar a imagem, o endereço ou deixar de disponibilizá-la; se isso ocorrer, o cartão informa que a fotografia real está indisponível. As embalagens mostradas são referências comerciais, e não recomendação clínica.


## Revisão responsiva de imagens (27/10/2026)
- Ajustadas as imagens dos cartões de medicamentos em telas estreitas: removida a ampliação forçada que podia cortar a base e as bordas das embalagens; agora o contêiner preserva a imagem inteira com `object-fit: contain`.
- Ajustadas as fotografias de Formas farmacêuticas, Acessibilidade e Sustentabilidade no celular para caberem por inteiro nos quadros, com fundo neutro quando sobrar espaço. O símbolo dos cartões de Acessibilidade também deixou de ficar cortado pela caixa da fotografia.
- Desativado o zoom por hover em dispositivos de toque para evitar que uma imagem fique ampliada/cortada após toque.
- Melhorados alvos de toque dos filtros, tamanho do título no celular e espaçamento das seções. Adicionado `scroll-margin-top` para que o menu fixo não cubra os títulos ao navegar.
- Corrigido o título visível e a descrição da página para “Entre. Explore. Escaneie. Aprenda.”


## Refinamento visual da caixa 3D do paracetamol (27/10/2026)
- Corrigidas as faces da caixa para não deixarem o cenário atravessar áreas transparentes do PNG original; os dois mapas de embalagem agora são opacos.
- Aplicado contorno discreto às arestas da caixa e da tampa, além de filetes na moldura frontal, para que os limites físicos permaneçam visíveis durante a rotação.
- Alinhada a tampa fechada com o topo do corpo, removendo a folga que deixava uma borda irregular. A face superior e a aba frontal usam cores coordenadas à embalagem. A profundidade foi ajustada para 0,44 unidade, coerente com a proporção da foto lateral.
- A lateral texturizada também está no lado visível ao iniciar a interação, evitando uma lateral lisa que parecia sem acabamento.
- Mantidas a rotação, o zoom, a abertura da caixa, a saída do frasco, a reinicialização e a bula interativa. Nenhuma alteração foi feita no modelo do frasco nem no conteúdo/controles da bula.

## Ajuste da caixa 3D (27/10/2026)
- A frente e as laterais da embalagem usam agora os arquivos originais `assets/paracetamol-box-user-front.png` e `assets/paracetamol-box-user-side.png` em painéis 3D separados e opacos.
- O núcleo da caixa mantém dimensões proporcionais à arte frontal e à arte lateral, com faces superior e inferior fechadas, verso próprio e arestas visíveis.
- O ângulo inicial foi ajustado para mostrar a frente e uma lateral ao mesmo tempo.
- A alteração é restrita à caixa; a geometria do frasco/xarope, a bula e as etapas de interação foram preservadas.


## Conteúdo legível na frente da caixa 3D (27/10/2026)
- Criada uma textura frontal própria em alta resolução (`assets/paracetamol-box-front-rotulo.png`), com o nome **paracetamol**, concentração **750 mg**, indicação de alívio da dor e febre, classes analgésico/antitérmico e forma **comprimidos**, baseada visualmente na embalagem frontal enviada para o projeto.
- A textura frontal passou a usar um novo nome de arquivo com versão para evitar que o GitHub Pages ou o navegador reaproveite uma imagem antiga em cache.
- A face frontal foi deslocada ligeiramente para a frente da caixa para se manter visível por cima do núcleo, sem alterar o modelo do frasco/xarope, a tampa, as laterais ou a bula.
- Incluída textura de contingência gerada em canvas caso a imagem frontal local falhe ao carregar, mantendo o nome e as informações principais visíveis.
- A arte frontal é uma representação educativa da embalagem; a fotografia original enviada continua preservada como arquivo separado.

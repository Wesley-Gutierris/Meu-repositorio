Atualizações - dia 15/01/2026

Meu projeto consiste em um dashboard fictício da sony, que que reflita dados anuais da assinatura PSPLUS e resultados da promoção de black Friday.
Iniciei hoje (15-01-2026) as primeiras fases do projeto. Meu primeiro passo foi criar uma planilha e todas as suas abas necessárias:

-Assets.
-Objetivos/perguntas de negócio.
-Bases da PSPLUS e Black friday.
-Uma tela inicial personalizada, utilizando como base a tela de login do Playstation 5.
-Duas planilhas de dash, onde cada uma poderá ser acessada via hiperlink.

Detalhes sobre o que foi feito hoje:
-Peguei alguns ícones e logos em PNG e colei na aba de assets.

-Com a ajuda da ferramenta "Just color picker" (Obrigado professor), consegui coletar algumas cores a serem utilizadas. As mesmas também se encontram na aba Assets.

-Garimpei a internet em busca de uma imagem de qualidade decente da tela de login do PS5. Com a ajuda da IA Gemini, editei a imagem para remover alguns elementos e editar o seu texto. Logo após, usei o site picwish para
aumentar a qualidade da imagem e remover a marca d'água do Gemini.

-Comecei a pensar nas estruturas das tabelas base. Para a base da PS Plus usei as seguintes colunas inicialmente:
*Internal user id
*User nickname
*Buy date
*Plan
*Subscription price
*Supscription type
*New user
*Renew

Decidi trabalhar com 1000 registros. Pedi ao copilot que gerasse uma planilha com 1000 User_id's, nicknames e datas de compra. Cuidei para que os Id's e nicknames não se repetissem.]

Logo após usei uma combinação de funções para gerar dados aleatórios de planos da PS plus, tipo de assinatura, se o usuário é novo e se é uma renovação:
=ESCOLHER(ALEATÓRIOENTRE(1;3);"PS PLUS ESSENTIAL";"PS PLUS EXTRA";"PS PLUS DELUXE")
=ESCOLHER(ALEATÓRIOENTRE(1;3);"Monthly";"Quaterly";"Annual")
=ESCOLHER(ALEATÓRIOENTRE(1;2);"Yes";"No") 

Após essas etapas, apliquei o valor "No" na coluna Renew para todos os usuários novos, para fazer sentido. 

Logo depois fiz uma chave composta com a assinatura + tipo de assinatura e cruzei os dados em outra tabela com os respectivos valores com um PROCV.


Após preencher todos os dados fictícios da primeira aba, comecei a pensar na base da black friday onde inicialmente usei as seguintes colunas:

*Internal user id
*User nickname
*Buy date
*Game
*Edition
*Promotional price

Para as datas de compra considerei a seguinte lógica:
-Promoção supostamente durou de 21/11/2025 até 29/11/2025.
-Inseri essas datas em duas celulas diferentes e depois mudei a formatação de número para "Geral", para obter os números correspondentes delas. Logo depois usei a função "aleatórioentre" com os dois números obtidos para obter datas de compra aleatórias.

-para fins de praticidade, usei os mesmo usuários da aba da PS PLUS.

-Fiz uma tabela base de jogos e preços e usei algumas funções para preenchimento aleatório no restante dos registros.

Por fim, montei algumas tabelas dinâmicas necessárias para o esqueleto do dashboard e finalizei o dia. 

_______________________________________________________________________________________________________________________________________________________________

Atualizações - dia 17/01/2026

Hoje fiz o dashboard das vendas da blackfriday.

Eu tinha uma ideia inicial na mente, mas ao tentar executá-la não ficou algo apresentavel. Mudei o rumo e tentei ser o menos redundante possível nas informações para não causar poluição visual. USei algumas tabelas dinâmicas fixas e outras váriaveis (conforme a segmentação) para os gráficos mudarem dinâmicamente.

Montei 4 cards que representassem KPI's importantes:
 *Total de vendas
 *Total de unidades vendidas
 *Ticket médio
 *% de crescimento de vendas de um dia para o outro.

 Este último foi necessário usar uma função "Se" bem grande para conseguir representar o valor corretamente no card, mas no fim deu tudo certo.

 Abaixo dos cards coloquei mais dois gráficos que os dados mudam conforme o dia e ediçao selecionada, um que representa o total de vendas por edição e outro que representa o top 10 diário dos jogos.

 Logo abaixo deles coloquei dois gráficos fixos, que representam o período como um todo. Um deles Contém os "best sellers", onde foquei apenas no top 5 e outro focado nas edições, fazendo um comparativo das duas ao mesmo tempo com um gráfico de linhas.

 Por fim, adicionei um botão de "Ir para", que direciona o usuário para o dash da PS plus.

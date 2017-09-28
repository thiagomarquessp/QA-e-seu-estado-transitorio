# QA e seu estado transitório

Obs.: Esse é um post que pode ir de encontro com opiniões, então, como não sou o dono da verdade, estou passando a minha opinião, minha visão, minha forma de viver tecnologia e qualidade de software. Respeito todas as opiniões e gostaria do mesmo tratamento =). Nem sempre da certo, mas estamos ai =).

Olá pessoal, esses dias eu passei por alguns bate papos e uma pessoa me questionou sobre o fato de ter uma média de um ano e meio em cada empresa que passei e passei a refletir sobre minha carreira profissional e no meu estágio, meu primeiro gestor e mentor me deu um conselho: De ser além de um excelente profissional tecnicamente falando, que eu deveria ser um profissional VERSÁTIL, ou seja, eu teria que entrar em uma empresa, deixar um legado e não me acomodar e com isso sair após esse legado para construir uma história de sucesso em outro lugar e é exatamente nisso que eu acredito. E essas conversas me levaram a escrever.

Bem, em minha andança, pude passar por dois tipo de processos: Waterfall e Agile e em diversos segmentos (Bancário, Telecom, Hospitalar, Cartões, Seguros, SAP, SaaS, IaaS, PaaS, MaaS, Empregabilidade, Workforce Planning) e o mais legal, é que as regras de negócio na atual empresa estão tão frescas como nomes de tabelas do VAS da Vivo por exemplo, ou então Identificação Positiva quando um cartão é passado numa ATM e consigo ver as informações do cliente como Agencia, Conta, CPF, etc através de um Log e por ai vai, assim como solicitar de forma emergencial um Stent ou Parafusos para uma cirurgia, ou então, cadastrar um material no SAP através da MM03 e todos seus impostos, enfim, todas as regras de negócio de todos os lugares eu sei e poderia voltar a qualquer momento que a "curva de aprendizado" seria zero.

Mas, dado que eu sei tudo isso, como foi que eu consegui ser um cara versátil e deixar um bom legado? É simples, tenho uma idéia fixa na cabeça que um QA é um CrossFunctional, ou seja, é único para disseminar conhecimento de qualidade por onde passa e a partir do momento que as pessoas dominam a disciplina, esse QA não é mais necessário. No meu caso, não sou um QA que gosta de pegar itens para testar no final de uma iteração, encontrar bugs no fim e ficar feliz com isso, eu sou um QA que gosta de antecipar os problemas para que eles não aconteçam e no fim da iteração, todos os cenários por mim mapeados foram implementados e quando eu executo esses testes, simplesmente o que era esperado, fora desenvolvido, conclusão: da-le produção.

Vamos lá, como nós QAs podemos antecipar problemas? 

Simples, estando próximo de todas as áreas que existem na empresa, não apenas da área de desenvolvimento e isso implica em estar em reuniões estratégicas do produto ou do negócio, para que nós possamos deixar nossa mente fluir com cenários e casos de teste, vendo possibilidades em como uma funcionalidade X ou Y podem quebrar na mão do usuário final (que em alguns casos, sermos nós mesmos o usuário final). Uma prática que eu tenho quando eu entro em qualquer empresa é conversar muito com as áreas de operações (que fazem um primeiro contato com o clinte), pois eu gosto de saber quais são os anseios dos nossos clientes, assim como eu gosto de saber os anseios e frustrações de quem opera também nosso sistema, pois eu acredito que vivendo o dia a dia de cada área da empresa nossa mente se expande e ficamos mais engajados com os problemas de todos. E claro, também estar próximo da área de TI, mas meu foco principal como quem gosta de qualidade, é saber que meu usuário final esteja feliz com que entregamos diariamente e depois pensar como tecnicamente posso fazer isso.

Mas só isso???

Não, após sua peregrinaçao nas diversas áreas da empresa, é hora de estarmos próximos da área de produto x desenvolvimento, e é exatamente aí que começa a ficar interessante nosso trabalho. Vou listar o que eu julgo ser de grande sucesso nessa empreitada: 

- Aproximação da área de produtos, pois começamos a entender de fato as entranhas do negócio ou do produto;
- Toda nova informação sobre o negócio, alimentar um Mind Map;
- Criar uma documentação viva através de Linguagem Funcional*, no caso, eu uso Gherkin num modelo de BDD, por exemplo: 
```ruby
Funcionalidade: Cadastro na loja

Eu, como futuro cliente da loja
Desejo realizar meu cadastro
Para realizar minhas compras

Cenário: Realizar cadastro com sucesso

Dado que eu acesse a página de cadastro de usuario
Quando eu preencher os campos obrigatórios
E clicar em cadastrar
Então deverei ser cadastrado com sucesso
```
- Apresentar o Gherkin implementado com algum framework a sua escolha. 

Geralmente o PO (Product Owner) ou PM (Product Manager) realizam o review das histórias criadas e vamos pensar nessa feature de cadastro na loja, imagina que para o PO ou PM realizar um cadastro, ele leva cerca de 5 minutos, até ai OK, agora, se ele precisar realizar 20 cadastros, ele vai levar só em cadastro 100 minutos ou 1:40 horas, que representa 17,5% do tempo apenas realizando cadastro, porém, esse mesmo cadastro em um fluxo automatizado vai levar uns 20 segundos, que vão ser 0:06 minutos de execução, que representa 0,75% do tempo (considerando um dia de 8 horas), ou seja, com esse argumento nós como QAs conseguimos plantar uma sementinha do bem, fazendo com que o PO ou PM enxergue nosso papel dentro do time, ou seja, consigo gerar insumos para que o trabalho de review do PO ou PM seja reduzido, e assim, uma feature ir de forma mais rápida para produção.

Ok, mas isso não é tudo .. esse é só o princípio porque para que eu consiga conseguir o apreço do PO ou PM, preciso sempre antecipar os problemas, e é aí que entra a aproximação com a equipe de desenvolvimento, e chega a hora que temos que plantar a sementinha do QA, e pra fazer isso é simples, primeiro de tudo, vendo PRs que os DEVs abrem, comentando algo caso você tenha conhecimento sobre melhores práticas de desenvolvimento ou então, olhando como eles fazem os testes unitários e de integração, e se você tiver conhecimento, questionar e tenho certeza que isso vai fazer com que o time começe a olhar pra você de outra forma. Depois é simples, lembra dos critérios de aceite em linguagem funcional que definimos com o PO ou PM? Pois é, essa é a hora de apresentar para os devs os cenários que você enxergou além dos critérios de aceite da US e incentive-os a desenvolver a feature baseada naqueles cenários, escrever os testes com base no que escrevemos, e se for o caso (pensando e em dev ruby OK), porque não escrever pra eles em formato RSPEC e simplesmente mostra pra eles, em algum momento, eles irão valorizar e vão desenvolver a feature também baseado nos critérios em formato gherkin e porque não, adotar um BDD, isso aos poucos vai ganhando valor, por exemplo, onde eu trabalho, temos bug zero no time que atuo mais "fortemente", pois toda a antecipação é feita, os critérios de aceite são apresentados em gherkin, eles entendem os anseios e os cenários, aplicam nos testes unitários e de integração, e, quando chega pra mim, apenas rodo os testes (que nesse momento já foram refatorados para novas features), deu tudo verde só colocar no CI e dá-le pra produção. 

Esse elo entre QA x DEV x PM ou PO acaba sendo uma engrenagem, onde todos se cobram, ou seja, sou cobrado por não aparecer no Planning sem os BDDs prontos para apresentar para os devs, a comunicação entre os devs e eu é constante, ou seja, qualquer ponto de dúvida quanto a testes, mesmo sendo pra executar uma bateria de testes para certificar que aquilo que está prestes a ir pra produção esteja funcionando em staging.

Quando você chega nesse patamar, onde o time abraçou qualidade, que PO e PM e Devs conseguem escrever BDDs ou pensar fora da caixa e implementar os testes, e alcançam um ponto onde em produção diariamente são feitas mais de uma entrega de valor, sem bugs, com PO e PM tranquilos para tocarem outras coisas e devs criarem coisas sempre inovadoras, essa é a hora exata que você deve ficar com sentimento de dever cumprido, e bora exercitar isso em outros lugares. Sair deixando um legado de qualidade de software, um legado de automação de testes, com todo o core automatizado, rodando na Integração Contínua, com PM e PO sabendo executar os testes que eles queiram fazer para simular uma situação e claro, com nosso cliente final satisfeito com nosso produto.

Eu não sou uma pessoa que se acomoda com locais de trabalho, minha natureza impede que eu entre nesse período de acomodação, como eu costumo falar, essa é minha visão sobre o que eu considero legal pra área de qualidade, eu tenho aplicado isso, tenho recebido alguns feedbacks negativos pois tem empresas que não tem essa mesma visão e ter uma pessoa que "pula de galho em galho" não é bom, mas sempre você encontra aquelas que pensam diferente, tipo, enquanto for bom pra nós, vai ser bom pra todos =).




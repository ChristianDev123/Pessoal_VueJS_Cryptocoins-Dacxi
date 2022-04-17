# Projeto DashBoard CryptoCoins Dacxi

## Tecnologias utilizadas:
- Vue 3 (CLI);
- Tailwind 3;
- Vue-Chart.js (Componentização do chart.js para vue);
- API CoinGecko (Fonte de dados de cotação de Criptomoedas);

## Passo-a-Passo para instalação do projeto:
> Certifique-se de já ter instalado o cliente git em sua máquina!

```CMD
git clone https://github.com/ChristianDev123/SPA_Dashboard_Cryptocoins_Dacxi.git
(Para instanciar uma copia do projeto)
```
```CMD
No Windows: cd SPA_Dashboard_Cryptocoins_Dacxi
(Para entrar no diretório do projeto)
```

```CMD
yarn add @vue/cli
    ou
npm install @vue/cli
(Instala a interface de linha de comando do vue, será necessário para comandar o projeto)
```

```CMD
yarn install
    ou
npm install
(Instala as dependências do projeto, ou seja as bibliotecas que o arquivo package.json aponta)
```

```CMD
yarn serve
    ou
npm run serve
(Incia o servidor de desenvolvimento da aplicação)
```

```browser
http://localhost:8080
(No navegador pesquise por esta url)
```

> Após configurar o arquivo vue.config.js para cada plataforma de deploy...

```CMD
yarn build
    ou 
npm build
(Inicia a criação de aquivos estáticos da aplicação, ou seja converte o código escrito em arquivos .vue em arquivos HTML, CSS e Java Script)
```

## Explicação de tomadas de decisões realizadas no projeto:

1. Criação da Prototipação da página.
    > A primeira decisão que tomei foi a criação da prototipação da página utilizando a ferramenta que mais tenho contato para este fim que é o Figma.
2. Design da página.
    > A princípio a escolha de um desing limpo e simples foi a minha primeira escolha. Já que a página contaria com gráficos e números. Uma tela poluída de informação com certeza atrapalharia o usuário e iria contra os princípios de UX desing.
3. Dark Theme (Tema Escuro).
    > Esta feature que hoje em dia está difundida em diversas aplicações que uilizamos no dia a dia é uma mão na roda a quem utiliza apps diariamente. Por este motivo optei por incorporar esta feature.
4. Paleta de cores
    > A paleta de cores predominantemente branco de azul foi inspirado no [site official da Dacxi](https://dacxi.com/). 
5. Código fonte da aplicação escrita em inglês
    > Pelo motivo de treinamento da utlização da lingua inglesa e pela maior facilidade de manutenção do código por pessoas não falante de lingua portuguesa decidi escrever o código fonte em inglês.
6. Gráfico
    > O Framework vue é muito novo para mim. Anteriormente minha experiência em frameworks Java Script estava restringido ao ReactJS e React-Native, por este motivo adicionei um desafio na task implementando um gráfico utilizando a lib chart.js.
7. Deploy na vercel
    > A vercel é uma ótima plataforma de deploy de aplicações front-end. E até então só havia utilizado o framework/biblioteca ReactJS nos projetos que hospedei na plataforma. Outro desafio pessoal seria subir um projeto em vue na plataforma.

### Explicações sobre o projeto
> Este foi o meu primeiro projeto desenvolvido no Framework Vue JS.
> Senti uma grande facilidade em utiliza-lo por conta de já ter experiência na utilização na biblioteca ReactJS.
> Este projeto foi Realizado com a finalidade de participar de um processo seletivo na empresa Dacxi.

___

# Translate for English

# Project DashBoard CryptoCoins Dacxi

##  Used technologies:
- Vue 3 (CLI);
- Tailwind 3;
- Vue-Chart.js (chart.js for Vue);
- API CoinGecko (Cryptocurrency quote data source);

## Step-by-step to project installation:
> Make sure you have already installed the git client on your machine!

```CMD
git clone https://github.com/ChristianDev123/SPA_Dashboard_Cryptocoins_Dacxi.git
(To instantiate an project copy)
```
```CMD
On Windows: cd SPA_Dashboard_Cryptocoins_Dacxi
(To entry on the path of project)
```

```CMD
yarn add @vue/cli
    ou
npm install @vue/cli
(Install vue's command line interface, will be necessary to command the project)
```

```CMD
yarn install
    ou
npm install
(Install all project's dependencies pointed by package.json)
```

```CMD
yarn serve
    ou
npm run serve
(Start the application development server )
```
```browser
http://localhost:8080
(On browser, search to this URL)
```
> After configuring the vue.config.js file for each deployment platform...

```CMD
yarn build
    ou 
npm build
(Start the create of static documents in language HTML,CSS and Java Script)
```

## Explicação de tomadas de decisões realizadas no projeto:

1. Creating the Page Prototype.
    > The first decision I made was to create the prototype of the page using the tool then I have most contact with for this purpose, I choose is Figma.
2. Design of the page.
    > At first, choosing a clean and simple design, this was my first choice. Since the page would have graphics and numbers. A screen polluted with information would definitely get in the way of the user and go against UX design principles.
3. Dark Theme (Dark Theme).
    > This feature, which is now widespread in several applications that we use on a daily. For this reason I chose to incorporate this feature.
4. Color palette
    > The predominantly white to blue color palette was inspired by the [Official Dacxi website](https://dacxi.com/).
5. Source code of the application written in English
    > Due to training in the use of the English language and the greater ease of code maintenance by non-Portuguese-speaking people, I decided to write the source code in English.
6. Chart
    > Framework vue is very new to me. Previously my experience in Java Script frameworks was restricted to ReactJS and React-Native, so this motivated a graphical challenge implementing to a task, the implementation challenge using the chart.js lib.
7. Depliy in Vercel
    > Vercel is a great front-end application deployment platform. And until then I had only used the ReactJS framework/library in the projects I hosted on the platform. Another personal challenge would be to upload a project in vue on the platform.

### Explanations about the project
> This was my first project developed in the Vue JS Framework.
> I felt easy to use it because I already have experience using the ReactJS library.
> This project was carried out with the aim of participating in a selection process at the Dacxi company.

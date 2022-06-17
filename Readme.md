# DashBoard CryptoCoins Dacxi

Este foi o meu primeiro projeto desenvolvido no Framework Vue JS. Foi Realizado com a finalidade de participar de um processo seletivo na empresa Dacxi.

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

## Imagens da aplicação:

![Imagem Dark Theme Aplicação](https://github.com/ChristianDev123/Pessoal_VueJS_Cryptocoins-Dacxi/blob/main/Dashboard_page-0001.jpg)

![Imagem Light Theme Aplicação](https://github.com/ChristianDev123/Pessoal_VueJS_Cryptocoins-Dacxi/blob/main/Dashboard_page-0002.jpg)

## Como instalar localmente:

> Certifique-se de já ter instalado o cliente git em sua máquina!

Siga os seguintes passos no CMD do Windows ou Bash do Linux:

```CMD
    git clone https://github.com/ChristianDev123/SPA_Dashboard_Cryptocoins_Dacxi.git
```
```CMD
    cd SPA_Dashboard_Cryptocoins_Dacxi
```
```CMD
    yarn add @vue/cli
        ou
    npm install @vue/cli
```
```CMD
    yarn install
        ou
    npm install
```
```CMD
    yarn serve
        ou
    npm run serve
```
```cmd
    start chrome http://localhost:8080
```

> Após configurar o arquivo vue.config.js para cada plataforma de deploy...

```CMD
    yarn build
        ou 
    npm build
```

## Tecnologias utilizadas:
- Vue 3 (CLI);
- Tailwind 3;
- Vue-Chart.js (Componentização do chart.js para vue);
- API CoinGecko (Fonte de dados de cotação de Criptomoedas);

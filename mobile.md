# Roadmap de Aprendizado em Desenvolvimento Mobile

Bem-vindo(a) ao Roadmap de Desenvolvimento Mobile! Este guia tem como objetivo orientar você, que está iniciando na área, pelos caminhos essenciais para se tornar um desenvolvedor mobile competente. Aqui você encontrará tópicos organizados, explicações sobre as principais tecnologias e frameworks, além de sugestões de projetos práticos.

---

## Sumário

- [Introdução](#introdução)
- [Pré-requisitos](#pré-requisitos)
- [Escolhendo a Plataforma: Android Nativo ou iOS com Swift](#escolhendo-a-plataforma-android-nativo-ou-ios-com-swift)
  - [Roadmap Android Nativo](#roadmap-android-nativo)
  - [Roadmap iOS com Swift](#roadmap-ios-com-swift)
- [Principais Frameworks de Desenvolvimento Mobile](#principais-frameworks-de-desenvolvimento-mobile)
  - [Flutter](#flutter)
  - [React Native](#react-native)
  - [Outras Opções](#outras-opções)
- [Projetos Sugeridos](#projetos-sugeridos)
- [Conclusão e Próximos Passos](#conclusão-e-próximos-passos)
- [Recursos Adicionais](#recursos-adicionais)

---

## Introdução

O desenvolvimento mobile é uma área em constante evolução e vital para empresas que buscam estar presentes no universo digital. Seja para criar aplicativos nativos com desempenho otimizado ou soluções multiplataforma que economizem tempo no desenvolvimento, este roadmap oferece uma visão prática e teórica para você iniciar sua jornada.

---

## Pré-requisitos

Antes de iniciar os estudos em desenvolvimento mobile, é recomendável ter uma base em:
- **Lógica de Programação:** Algoritmos, estruturas de dados e conceitos de programação.
- **Conceitos de Orientação a Objetos:** Fundamentos que serão úteis em diversas linguagens.
- **Conhecimentos Básicos em HTML, CSS e JavaScript:** Úteis, inclusive, para entender frameworks híbridos.

Caso ainda não possua esses conhecimentos, procure cursos introdutórios de Ciência da Computação e programação.

---

## Escolhendo a Plataforma: Android Nativo ou iOS com Swift

Uma das primeiras decisões a tomar é em qual plataforma você deseja se especializar. Este roadmap sugere começar pelo desenvolvimento nativo, utilizando **Android** (com Kotlin) ou **iOS** (com Swift).

### Roadmap Android Nativo

1. **Fundamentos do Android Kotlin:**
   - Instale e configure o [Android Studio](https://developer.android.com/studio).
   - Aprenda os conceitos básicos **Kotlin** (ainda é possível fazer com Java, mas limitado a UI usando XML e não é uma linguagem recomendada mais. Codigos Kotlin e Java conseguem "conversar entre si" aqui).
   - Estude a arquitetura básica do Android: Activity, Fragment, ciclo de vida, intents e recursos.

2. **Desenvolvimento de Interface e Layouts:**
   - Aprenda a trabalhar com XML para criar layouts.
   - Entenda o uso de ConstraintLayout, RecyclerView, ListView, e outros componentes UI.
   - Depois de ter estudado a base do XML: Estude Jetpack Compose, que é o framework de UI recomendado atualmente.

3. **Persistência de Dados:**
   - Para Bancos de Dados Simples (chave-valor):
      1. SharedPreferences
      2. DataStore (abstração do SharedPreferences)

   - Para Bancos de Dados Simples (chave-valor), mas com criptografia:
      1. EncryptedSharedPreferences

   - Para Bancos de Dados Complexos:
      1. SQLite (banco de dados complexo SQL nativo no Android)
      2. Room (abstração do SQLite)


4. **Comunicação e API REST:**
   - Antes de tudo: entenda o que é um JSON e qual a relação dele com a conectividade remota de um aplicativo. Entenda que Bancos de Dados Remotos geralmente recebem e enviam informações usando o padrão JSON.
   - Entenda como é implementada as requisições HTTP nativas no ambiente Android (são usando OkHttp). Aqui você precisa entender quem é o Client HTTP e a possibilidade de adicionar interceptadores (como por exemplo de Logs).
   - Comece a fazer requisições usando bibliotecas:
   elas facilitam muito o desenvolvimento, tornando mais simples e rápido de escrever e fazer as requisições
      - Utilize bibliotecas como Retrofit para consumo de APIs.
      - Pratique o tratamento de JSON com Gson ou Moshi (Gson é o mais usado). Aqui você deve entender que está sendo feita uma 'tradução' do código de Kotlin para JSON e de JSON para Kotlin. Funciona de forma muito mágica, mas você deve entender que isto está acontecendo.
   - Evolua nas requisições:
      - Entenda com maior profundidade como elas funcionam substituindo o Retrofit pelo KtorClient, e esteja preparado para fazer apps que funcionam no Kotlin Multiplataforma.
      - Substitua Serialização de JSON 'Gson' por Kotlin Serialization, e faça Encode e Decode de JSON usando recuros nativos do Kotlin, e que funcionam no Kotlin Multiplataforma.

5. **Testes e Debug:**
   - Ferramentas de depuração e uso do Logcat: aprenda a colocar Logs no código e usar breakpoints para te auxiliar a procurar erros e monitorar a execução do código
   - Testes Unitários usando JUnit
   - Testes de UI usando Compose UI Test (para Compose) ou Mockito para XML.
   

6. **Boas Práticas e Publicação:**
   - Estude padrões de projeto (MVVM, MVP, MVC). No Android, o mais usado e recomendado é MVVM.
   - Adicione a camada 'Repository' no seu projeto MVVM. O padrão Repository é amplamente usado.
   - (Opcional) Aplique conceitos de Clean Architecture no seu Projeto MVVM com Repository Pattern: separe em Presentation, Domain e Data. Clean no Android usa apenas 3 camadas.
   - Aprenda sobre gerenciamento de versões, testes em diferentes dispositivos e publicação na Google Play Store.

### Roadmap iOS com Swift

1. **Fundamentos do iOS e Swift:**
   - Instale o [Xcode](https://developer.apple.com/xcode/).
   - Aprenda os conceitos básicos da linguagem **Swift** e da programação orientada a objetos.
   - Conheça a estrutura de um projeto iOS, Storyboards e SwiftUI (dependendo do seu interesse).

2. **Desenvolvimento de Interface e Layouts:**
   - Trabalhe com Interface Builder ou SwiftUI para criação de layouts responsivos.
   - Entenda Auto Layout, stacks e componentes de interface (Buttons, Labels, TableViews).

3. **Persistência de Dados:**
   - Explore UserDefaults, CoreData e outros métodos de armazenamento.

4. **Comunicação e API REST:**
   - Aprenda a usar URLSession para fazer requisições HTTP.
   - Gerencie dados com JSONDecoder e outras técnicas de parsing.

5. **Testes e Debug:**
   - Desenvolva testes unitários e testes de interface.
   - Utilize ferramentas de debugging do Xcode.

6. **Boas Práticas e Publicação:**
   - Estude padrões de arquitetura (MVC, MVVM, VIPER).
   - Prepare-se para o processo de submissão na App Store, incluindo certificações e guidelines da Apple.

---

## Principais Frameworks de Desenvolvimento Mobile

Além do desenvolvimento nativo, existem frameworks que permitem criar aplicativos para múltiplas plataformas com uma única base de código. Esses frameworks podem ser um excelente complemento à sua formação.

### Flutter

- **Descrição:** Desenvolvido pelo Google e escrito em Dart, o Flutter permite criar aplicativos nativos para Android, iOS, web e desktop.
- **Pontos Fortes:** 
  - Desenvolvimento multiplataforma com performance nativa.
  - Rica biblioteca de widgets personalizáveis e recarregamento a quente (hot reload).
- **Mini Roadmap:**
  1. Instalar o Flutter SDK e configurar o ambiente.
  2. Aprender a linguagem Dart.
  3. Criar e estilizar widgets.
  4. Gerenciar estado e fazer integração com APIs.
  5. Publicar o aplicativo nas lojas.

### React Native

- **Descrição:** Desenvolvido pelo Facebook e baseado em JavaScript (ou TypeScript), o React Native permite criar aplicativos nativos para Android e iOS.
- **Pontos Fortes:**
  - Permite compartilhar grande parte do código entre plataformas.
  - Grande comunidade e vasta quantidade de bibliotecas.
- **Mini Roadmap:**
  1. Configurar o ambiente com Node.js, npm e React Native CLI (ou Expo para projetos mais simples).
  2. Aprender os fundamentos do React e JSX.
  3. Desenvolver componentes e gerenciar estado.
  4. Integrar com APIs e utilizar bibliotecas nativas quando necessário.
  5. Testar e otimizar o desempenho do aplicativo.

### Outras Opções

- **Xamarin:** Para quem tem familiaridade com .NET e C#, permite criar aplicativos nativos com compartilhamento de código. (Observe que, dependendo da experiência, alguns relatos indicam desafios na prática.)
- **Ionic:** Baseado em tecnologias web (HTML, CSS, JavaScript), é ideal para quem já tem experiência com desenvolvimento web e deseja criar aplicativos híbridos.

---

## Projetos Sugeridos

Para colocar em prática o que você aprendeu, seguem algumas ideias de projetos:

1. **App de Lista de Tarefas (To-Do):**
   - Desenvolva um aplicativo simples para gerenciamento de tarefas com CRUD (criar, ler, atualizar e deletar).
   - Incorpore persistência local (SQLite ou CoreData) e consumo de uma API para sincronização.

2. **App de Clima:**
   - Crie um aplicativo que consuma uma API pública de clima e exiba informações atualizadas.
   - Trabalhe com layouts responsivos e animações simples.

3. **App de Notícias:**
   - Desenvolva um agregador de notícias que consome diferentes fontes via API.
   - Implemente paginação, filtros por categoria e sistema de favoritos.

4. **App de Finanças Pessoais:**
   - Crie uma aplicação para controle de despesas e receitas.
   - Inclua gráficos e relatórios simples para visualização dos dados.

5. **Projeto Multiplataforma com Flutter ou React Native:**
   - Escolha um dos frameworks mencionados para desenvolver um aplicativo que rode em Android e iOS.
   - Explore as diferenças entre o desenvolvimento nativo e o uso de frameworks multiplataforma.

---

## Conclusão e Próximos Passos

Este roadmap oferece uma visão ampla e organizada dos caminhos que você pode seguir para se tornar um desenvolvedor mobile. Lembre-se de que a prática é fundamental: quanto mais projetos você desenvolver, mais consolidará seus conhecimentos. Reserve um tempo para estudar a documentação oficial de cada plataforma e framework, participe de comunidades e fóruns (como GitHub, Stack Overflow e grupos no Reddit) e mantenha-se atualizado com as novidades do setor.

---

## Recursos Adicionais

- **Documentação Oficial:**
  - [Android Developers](https://developer.android.com/)
  - [Apple Developer](https://developer.apple.com/)
  - [Flutter](https://flutter.dev/docs)
  - [React Native](https://reactnative.dev/docs/getting-started)

- **Cursos Online e Tutoriais:**
  - Plataformas como Udemy, Coursera, Alura e Digital Innovation One oferecem cursos direcionados para desenvolvimento mobile.
  
- **Comunidades e Fóruns:**
  - Participe de grupos no Reddit, fóruns especializados e comunidades no Discord para trocar experiências e tirar dúvidas.

---

Este README.md serve como um guia inicial, mas lembre-se: a jornada de aprendizado é contínua. Adapte os tópicos conforme seu ritmo e interesse, e não hesite em buscar mais informações e desafios à medida que avança.

Bons estudos e sucesso na sua jornada como desenvolvedor mobile!

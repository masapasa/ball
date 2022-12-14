---
title: "Multi-cloud: o que, quando e para quem?"
description: Além de multiclouds, há multi conceitos de multicloud. Uma análise de abordagens.
featured: true
pubDate: "2021-05-28T10:50:00.000Z"
image: ~/assets/images/multicloud.png
socialImage: "/features/multicloud-page.png"
---

<p class="lead">Multi-cloud como estratégia é um tópico que vem se tornando cada vez mais comentado. Mas, ao mesmo tempo o termo ganha polissemia,significando coisas diferentes, para pessoas diferentes e para além de qualquer discussão semântica, a definição concreta do termo é o primeiro passo, melhor, ainda que hajam definições concorrentes, que fique bem claro as implicações bem práticas desse tipo de estratégia que altera não somente as decisões de tecnologia, mas impacta a própria cultura dos times e das organizações. </p>

## Definindo multi-cloud

Antes de mais nada, é importante definições claras. Existem _definições_ e _definições_ de multi-cloud.Então acredito que precisamos explorar cada ângulo e tentar extrair os _trade-offs_. Eu vivo pela regra de ouro de que se você ainda não encontrou  os _trade-offs_ de uma alternativa você só não os encontrou _até o momento_.

## Talvez você já tenha uma estratégia multi-cloud

O [episódio 99](https://www.serverlesschats.com/99/) do [podcast Serverless Chats](https://www.serverlesschats.com/) foi inclusive sobre este tema e a discussão entre Robin Sutter, Principal Developer Advocate na [Fauna](https://fauna.com/) e seu apresentador, [Jeremy Daly](https://www.jeremydaly.com/) [AWS Serverless Hero](https://aws.amazon.com/developer/community/heroes/jeremy-daly/) e que mantém a excelente newsletter [Off-by-none](https://offbynone.io/).

> Multicloud is not cloud-agnostic. We're not talking about running the same work load in parallel on multiple service providers or whatever.We're talking about this idea of using the best services that are available to you across the spectrum of providers, whether those are cloud service providers, whether those are SaaS companies, or even to some degree, some open-source projects that are out there that make up this strategy.
> <footer><a href="https://twitter.com/rts_rob" target="_blank">Jeremy Daly</a></footer>

<iframe width="560" height="315" src="https://www.youtube.com/embed/CUx1KMJCbvk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

> Well, it's sort of a dirty word today, and people like to rail against it. I think rightly so because it's that multicloud 1.0, the idea of, as you said, cloud-agnostic that **"write once, run everywhere."** All that is, is a race to the bottom, right? It's the lowest common denominator. It's, "What do I have available on every cloud service provider? And then let me write for that as a risk management strategy." **That's a cost center when you want to put it in business terms. You're not generating any value there. You're managing risk by investing against that.**
> <footer><a href="https://twitter.com/rts_rob" target="_blank">Rob Sutter</a></footer>

Honestamente eu tenho minhas dúvidas a respeito de que seja "multi-cloud 1.0" um conceito ultrapassado. Me parece ao menos nos principais resultados de pesquisa, ao menos em português, junto com anúncios, o conceito dominante em nosso uso. E como Rob explora, eu acredito que é um centro de custo. Não que cada contexto e organização não tenham suas particularidades e complexidades, mas é inegável que de um ponto de vista estratégico, essa definição dominante, não é superior e sim, contraditória. Também explorada pelo _Cloud Economist_ [Corey Quinn](https://twitter.com/QuinnyPig) em [Multi-Cloud is the Worst Practice](https://www.lastweekinaws.com/blog/multi-cloud-is-the-worst-practice/). Algumas companhias, principalmente que investem pesado em modelos de licenciamento e/ou virtualização como _core_ do negócio, são extremamente vocais em estabelecer esse modelo de multi-cloud como uma espécie de **Lift & Shift**.

> I would also say that multi-cloud does make sense for different workloads that have very few points of interaction, especially if they’re already built to embrace the benefits that one cloud provider offers over another. I don’t really have a problem with that. My anti-multi-cloud stance—which I feel like it gets misinterpreted a fair bit—is, “We’re going to build one workload that we could seamlessly move between cloud providers, even though we either never do it or we’re trying to do it for the wrong reasons.” That’s the multi-cloud that I’ve seen being pushed by a variety of vendors and that’s the thing that upsets me.
> <footer><a href="https://twitter.com/QuinnyPig" target="_blank">Corey Quinn</a></footer>
 
Eu entendo como em empresas com processos de decisão demorados e avessos ao risco, esse seja um caminho e uma estratégia bem atraente. Mas não deixa de ter muita fricção na operação desse modelo. Geralmente as nuvens públicas possuem alguns recursos padrão bem parecidos, mas nunca existem mapas 1:1 entre as mesmas e acabam tendo que fazer soluções próprias para que a arquitetura se sustente. O que no longo prazo tende a se tornar débito técnico, pois não utilizam o melhor de cada provedor e se não pensado corretamente, com os custos de dados de transferência _egress_ podem facilmente se perder os controles dos custos. Eu não recomendaria esta estratégia a nenhuma empresa pequena, startup ou times de tecnologia dentro de empresas a não ser que seja um imperativo que não há outra escolha. O relato de [Alan Raison](https://twitter.com/alanraiso), bem franco e transparente para o episódio [When Two Clouds Isn’t Enough with Alan Raison](https://www.lastweekinaws.com/podcast/screaming-in-the-cloud/when-two-clouds-isn-t-enough-with-alan-raison), que em seu dia a dia lida com três provedores de nuvem pública.

> In contrast, what you and I are talking about today is this idea of, **"Let me use best in class everywhere,"** and that's a **value generation strategy**. This cloud service provider offers something that this team understands, and wants to build with, and creates value for the customer more quickly. So they're going to write on that cloud service provider. This team over here has different needs, different customers. Let them write over there. Quite frankly, a lot of this is already happening today at medium businesses and enterprises. **It's just not called multicloud.**
> <footer><a href="https://twitter.com/rts_rob" target="_blank">Rob Sutter</a></footer>

<figure class="extend">
    <img src="/assets/gartner.jpeg" width="752" height="475" alt="AWS lidera o mercado de Cloud" style="border: 1px solid #BBB" />
    <figcaption>Por dez anos seguidos, a AWS lidera o mercado de Cloud no quadrante Gartner</figcaption>
</figure>

## Qual usar?

Minha experiência de seis anos, tirando alguns testes aqui e ali, são focados na AWS. Eu sou um _AWS Community Builder_, _Solutions Architect Associate_ certificado e grande entusiasta pricipalmente do poder do **Serverless** como uma forma de criação de valor. Então, o melhor conselho que posso dar é: utilize a AWS. Entretanto, avalie especialistas de outras clouds, gaste um tempo experimentando. É uma grande decisão. Uma startup que nem encontrou seu _product-market-fit_ não tem porque ter uma estratégia multi-cloud. Ou melhor, se tiver isso seria uma distração, além de aumentar os custos. Nunca otimização de custos será uma determinante em adotar multi-cloud, a não ser que existam contratos de licenças legadas – mas isso eu atribuo mais à perversidade de um _lock-in_, este sim. Muitas vezes tratam o _vendor lock-in_ de nuvens como o principal assunto e acho que é um pouco desfocado esse argumento. Se trata do custo de mudança. Se eu tiver uma arquitetura baseada em eventos, _declouped_ talvez eu consiga alterando algumas partes migrar da AWS para a Azure, mas se eu tenho licenças _por máquina_ de um software, eu não tenho na verdade muita opção. 

A Microsoft é a empresa que mais tem me surpreendido nos últimos anos por sua grande reviravolta em percepção dos desenvolvedores. VSCode se tornou ubíquo, adquiriu o GitHub e por extensão, o NPM, tão importante para o ecossistema JavaScript – e também tendo contribuído com o próprio TypeScript. A ascensão da Azure nos próximos anos será cada vez mais uma constante.

O Google, cuja cultura de performance e engenharia eu aprecio entretanto me traz dúvidas. Em fevereiro de 2021 vários veículos abordaram a [perda de bilhões que a Google estaria tendo com o Google Cloud](https://techcrunch.com/2021/02/02/google-cloud-lost-5-6b-in-2020/). E, bem, quem melhor do que um ex-Googler, Steve Yegge em seu post [Dear Google Cloud: Your Deprecation Policy is Killing You](https://steve-yegge.medium.com/dear-google-cloud-your-deprecation-policy-is-killing-you-ee7525dc05dc), somente deu mais peso para minhas dúvidas. Custos surpresa em despesas na nuvem são uma constante preocupação de qualquer gestor. Uma startup [consumiu 72.000 USD em 2 horas na Google Cloud](https://blog.tomilkieway.com/72k-1/). O mais chocante para mim da notícia é que um dos fundadores _trabalhou_ no Google. Óbvio que fatos anedóticos, podem não ser a melhor forma de analisar uma opção, mas diretamente afetam a percepção das pessoas e nem todos do seu time podem ter a visão completa. Costumo dizer que em todo projeto há 2 sistemas: _o-sistema-como-é_ e _o-sistema-como-imaginado_, entendendo sistema aqui também mais do que uma aplicação mas o complexo sócio-tecnológico de pessoas desenvolvendo, dando manutenção, intermediando ações programáticas e os usuários dessa aplicação. Ignorar o _o-sistema-como-imaginado_ é uma receita para o desastre. E o Google movendo o G-Suite e suas APIs para o Google Cloud, o que, é claro, faz muito sentido, como um usuário corporativo desses serviços, francamente me deixa com certa dúvida, como se não houvesse uma clareza para mim de como estes serviços estarão em 5 anos.

Resta o que a Gartner chama de **niche players**: empresas que focam em um pequeno segmento **ou** são desfocadas e não possuem performance melhor e/ou inovam mais que outras. O _ou_ na definição da Gartner acredito que nos apresenta um interessante _baseline_ para classificar os esforços das empresas. Focar em um segmento pequeno não significa entretanto que não tenha muito potencial financeiro, apenas a otimização para um determinado tipo de carga de trabalho. Que pode ser exatamente o que você precisa.

A resposta de qual nuvem utilizar acaba sendo um dos grande adágios de software: _Depende_.

E você, qual é a <span role="img" aria-label="nuvem">☁️</span> que você resolveu adotar e por quê? Vamos dialogar!
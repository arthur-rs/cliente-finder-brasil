---
name: cliente-finder-brasil
description: >-
  Encontra e qualifica, com evidência, os primeiros clientes potenciais de um
  produto no mercado brasileiro a partir de sinais públicos recentes (Facebook,
  Instagram, LinkedIn, YouTube, TikTok, Reclame Aqui, Mercado Livre, Google
  Maps, X, fóruns BR, vagas). Também serve para infoproduto low ticket: acha as
  frases reais de dor do público para virar ângulo de criativo. Use em
  "ache meus primeiros clientes", "quem compraria isso", "ache leads",
  "ache parceiros de teste", "onde está meu público", "pesquisa de público",
  "ângulos para criativo", ou quando receber a URL de um produto e pedirem quem
  usaria ou pagaria por ele. Só pesquisa: define o cliente ideal, garimpa
  sinais públicos, pontua, rascunha abordagens e gera relatório HTML. Nunca
  envia mensagem nem contata ninguém.
---

# Cliente Finder Brasil

Transforma a URL ou a descrição de um produto numa lista curta, com evidência, de clientes potenciais no Brasil. Todo prospect precisa vir de um sinal público real que você abriu e conferiu na fonte original. A lista é uma hipótese de pesquisa, não um banco de clientes.

Leia [references/research-framework.md](references/research-framework.md) antes de pesquisar ou pontuar. Leia [references/report-schema.md](references/report-schema.md) antes de gerar o relatório.

Escreva tudo (relatório, mensagens, análise) em português do Brasil, com o vocabulário do público.

## Fluxo

### 1. Entender o produto

Abra a URL (e as páginas de preço/sobre, se existirem) ou leia a descrição. Defina: o que o produto faz, o resultado que vende, quem usa e quem paga, preço e forma de compra (Pix, boleto, cartão, assinatura, Hotmart/Kiwify/Eduzz), região do Brasil se importar, e o caso de uso mais forte.

Escolha **um cliente ideal principal e um adjacente**, cada um com gatilhos de dor, sinais positivos e desqualificadores explícitos. Em produto de dois lados, o principal é o lado que paga. Marque o que foi inferido e não observado. Faça uma pergunta ao usuário só se a dúvida mudar onde pesquisar.

Escolha o modo (veja **Modos**). Se o produto custa até ~R$ 100 e é vendido por anúncio (infoproduto, PDF, curso curto, low ticket), use o modo **infoproduto** por padrão: falar com 10 pessoas uma a uma não paga a venda, o valor está nas frases de dor que viram anúncio.

### 2. Espalhar a busca de sinais

Rode os cinco grupos de busca do framework (demanda explícita, dor, gambiarra, troca, momento) como **subagentes de pesquisa em paralelo**, um grupo por agente, cada um devolvendo sinais com URL, data e resumo fiel. Passe a cada agente o resumo do produto e o cliente ideal para que ele descarte matches fracos na origem. Cada agente precisa abrir e citar as fontes: não pode devolver URL que não abriu. Sem suporte a subagentes, rode os grupos em sequência.

Varie as fontes entre agentes usando o **mapa de fontes do Brasil** do framework. Pesquise em português, com gírias e o jeito que o público fala ("alguém indica", "tô sofrendo com", "socorro", "vale a pena?"). Para B2B, inclua LinkedIn; para consumidor final, priorize Facebook, Instagram, YouTube, TikTok e Reclame Aqui.

### 3. Verificar antes de qualificar

Abra a página original de todo sinal antes de ele entrar na lista. Trecho de busca, resumo de agregador ou paráfrase de subagente sem citação não é evidência. Confira se a página existe, se diz o que foi alegado, e a data. Descarte o que falhar. Registre URL, tipo de fonte, data visível (ou "data indisponível") e o que foi observado versus inferido. Quando um subagente já citou a fonte, faça amostragem — e sempre reverifique os três primeiros você mesmo.

Facebook, Instagram, LinkedIn, TikTok e Reclame Aqui costumam bloquear acesso automático no servidor. Não descarte um candidato só por isso: verifique por outra via legítima — a sessão de navegador do usuário (se houver ferramenta de navegador), a busca do Google restrita ao site (`site:facebook.com/groups ...`) seguida de abrir o link no navegador, ou a versão pública da página. Anote por qual via verificou.

Limites de pesquisa (inegociáveis):

- Só informação pública, compartilhada de propósito, profissional ou de negócio.
- Nunca burle login, paywall, limite de acesso ou robots. Grupo privado de Facebook, grupo de WhatsApp e grupo fechado de Telegram estão fora.
- Sem bases compradas, listas vazadas, "mailing", scraping de contatos, consulta de CPF, e-mail ou telefone pessoal.
- CNPJ e dados públicos de empresa (Receita Federal, site da empresa, Google Maps) podem ser usados em B2B. Dados de pessoa física, não.
- Nunca infira nem use dados sensíveis (LGPD art. 5º, II): saúde, religião, política, orientação sexual, raça, finanças pessoais. Isso vale mesmo quando o produto é de saúde ou religioso: pesquise o tema e a comunidade, não marque pessoas por isso.
- Parafraseie por padrão; cite pouco; dê link de todo sinal relevante.

### 4. Pontuar e enxugar

Pontue cada prospect verificado com a régua do framework (dor, encaixe, momento, alcançabilidade, evidência → 0–100). Tire duplicados. Prospect abaixo de 50, ou sem sinal citado de dor/demanda/momento, não entra na lista principal — só bater com o perfil é especulação.

Nunca diga nem sugira que um prospect tem interesse, deu consentimento ou vai comprar. Rotule tudo como "cliente potencial com base em sinais públicos".

### 5. Rascunhar abordagem — nunca enviar

Para cada prospect, sugira o canal mais natural já ligado à fonte (responder no post ou comentário, perfil público, página de contato da empresa, WhatsApp comercial divulgado publicamente pela empresa) e escreva uma mensagem de até 90 palavras, em tom brasileiro, próximo e sem cara de robô: cite o contexto público com naturalidade, ligue ao problema exato, descreva o produto em uma frase, termine com uma pergunta leve. Use só o que está na fonte — sem intimidade fingida, sem dado pessoal. Nada de "Prezado(a)".

No modo **infoproduto**, troque a mensagem por um **ângulo de criativo**: o gancho de 1 linha tirado das palavras do público e a frase de dor que ele usou.

Não envie mensagens, não preencha formulários, não comente, não siga, não conecte, não crie registro em CRM. Se o usuário pedir para enviar, é outro pedido que precisa da autorização explícita dele, mensagem por mensagem.

### 6. Gerar o relatório

Por padrão, relatório HTML (só no chat se o usuário pedir):

1. Escreva a análise em JSON conforme [references/report-schema.md](references/report-schema.md) numa pasta temporária.
2. Rode `python3 scripts/generate_report.py <analise.json> <saida.html>` (no Windows, `py` em vez de `python3`; o script fica na pasta desta skill e só usa biblioteca padrão).
3. Salve o relatório em `outputs/` no projeto e devolva o caminho absoluto clicável.
4. Abra o HTML e confira: cards dos prospects aparecem, todo link é URL real, notas batem com a régua, padrões e plano de sete dias estão lá.

No chat, comece pelo veredito e pelo prospect mais forte, depois o link do arquivo.

## Modos

- **rápido** — até 5 prospects fortes.
- **padrão** — até 10 prospects em vários tipos de fonte.
- **profundo** — até 20 prospects e mapa de dores repetidas.
- **infoproduto** — para low ticket vendido por anúncio (Meta, TikTok, YouTube). O "prospect" passa a ser a **comunidade ou publicação** onde a dor aparece (um post viral, uma thread de comentários, um grupo público, uma reclamação). Foque em: frases literais de dor, objeções ("será que funciona?", "é golpe?", "muito caro"), o que já tentaram, e quem compra para quem (ex.: filha comprando para a mãe). Os **padrões** viram os ângulos de anúncio; o plano de sete dias vira quais criativos testar primeiro. Sugira também interesses e palavras para segmentação.
- **parceiros-de-teste** — prioriza quem vai testar e dar feedback sobre quem vai pagar.
- **b2b** — prioriza empresas, gatilhos públicos de negócio (vaga aberta, nova filial, CNPJ novo, mudança de lei) e cargos que decidem; LinkedIn em primeiro lugar.
- **comunidade** — prioriza discussões públicas e pedidos explícitos de "alguém indica?".
- **local** — negócio físico ou de cidade: Google Maps, Instagram local, grupos públicos do bairro/cidade, OLX.

## Pegadinhas

- **Inventar é o que mata esta skill.** Um prospect plausível com link morto ou que não bate é pior que nenhum. A verificação (passo 3) é obrigatória, até no modo rápido.
- **Produto de dois lados:** os subagentes vão trazer os dois lados misturados. Filtre para o cliente principal antes de pontuar; o lado adjacente vai em padrões.
- **Sinal velho:** um pedido explícito de 18 meses atrás ainda pode entrar, mas corte a nota de momento e mostre a data.
- **Dez fortes valem mais que trinta genéricos.** Se a verificação deixar quatro ótimos, entregue quatro e diga por quê.
- **Golpe e desconfiança:** no Brasil, "é golpe?" é objeção nº 1 em produto digital. Registre quando aparecer; é sinal de padrão, não de desinteresse.
- **Pressa:** se o usuário pedir para acelerar ou fechar no meio, mude para o modo rápido na hora: pare de esperar grupos inacabados, verifique e pontue o que já tem, e entregue o relatório dizendo quais grupos ficaram incompletos.

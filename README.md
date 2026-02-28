

# PRD - Aplicativo de Organização de Finanças Pessoais
- Este projeto foi desenvolvido como desafio de projeto da DIO utilizando vibe coding a partir da utilização do copilot e Lovable. A proposta é criar um aplicativo de organização financeira pessoal baseado em interações em linguagem natural.

---
## 0. Identidade do contato
- Nome do solicitante: Waldevino Paulo

## 1. Contexto e objetivo
Objetivo: permitir que usuários iniciantes controlem receitas, despesas e metas financeiras por meio de conversas em linguagem natural, com visualização em blocos (estilo Power BI) e design universal para máxima inclusão.
Valor entregue: redução de atrito no registro de despesas; insights acionáveis; metas financeiras simples e visíveis.

## 2. Público-alvo
- Primário: pessoas iniciando controle de gastos.
- Secundário: usuários que preferem interação por voz, pessoas com baixa familiaridade digital, idosos e usuários com necessidades de acessibilidade.
- Requisito transversal: suporte a múltiplos níveis de letramento financeiro e diferentes dispositivos (celular, tablet).

## 3. Informações exibidas na tela principal (dashboard)
A tela principal deve apresentar, de forma clara e acessível, os seguintes blocos de informação:
1. Receitas
2. Despesas
3. Metas

A tela principal deve exibir os blocos: Receitas, Despesas e Metas e os gráficos correspondentes às despesas iniciais:
- Transporte
- Alimentação
- Lazer
- Vestuário
- Compras

Observação: cada categoria será representada por um **ícone quadrado** com a imagem correspondente.

## 4. Fluxos de interação relevantes

### 4.1 Categorizar uma despesa
- Ao clicar no botão para categorizar uma despesa, o usuário vê uma tela de seleção de categoria.
- Cada categoria é apresentada como um **cartão com ícone quadrado** (imagem correspondente) e rótulo.
- O usuário pode selecionar uma das categorias existentes tocando no cartão.
- Se o usuário optar por **criar uma nova categoria**, o sistema:
  - Gera automaticamente um **ícone padrão** (ícone quadrado com imagem genérica).
  - Permite que o usuário **substitua a imagem** do ícone posteriormente, buscando uma imagem na internet ou escolhendo uma imagem do aparelho/computador (fluxo de alteração de imagem).
  - Permite nomear a nova categoria e salvar.
- Histórico de categorias personalizadas deve ser editável e removível.
- Regras de segurança para imagens externas: aplicar filtros de conteúdo, verificação de licenças e orientação ao usuário sobre direitos autorais; oferecer biblioteca de ícones licenciados como alternativa.

### 4.2 Adicionar e acompanhar metas
- Ao criar uma meta, o usuário escolhe:
  - **Valor final** desejado.
  - **Tempo** para atingir esse valor (qualquer valor entre 1 dia e 1 ano).
- O app calcula automaticamente o **aporte mensal necessário** para atingir a meta no prazo definido.
- O app apresenta um **gráfico de progresso** que mostra:
  - Valor acumulado até o momento.
  - Projeção de aportes mensais necessários.
  - Percentual atingido em relação à meta.
- O usuário pode editar valor e prazo da meta a qualquer momento; o aporte mensal e o gráfico são recalculados.

### 4.3 Interação com gráficos por categoria
- Na tela de relatório por categoria (ex.: “Último mês”), o usuário pode filtrar/exibir uma categoria por:
  - Comando verbal (ex.: “Me mostra só os gastos com transporte”).
  - Mensagem escrita (ex.: “Quero ver os gastos com alimentação”).
  - Toque direto no gráfico (clicar na barra ou segmento).
- A tela de relatório por categoria não deve exibir botões de registro; é apenas visualização e o controle de tempo.
- Abaixo dos gráficos, incluir controle deslizante (slice) para período entre 1 dia e 1 ano, com pontos sensíveis: 1 semana, 15 dias, 1 mês, 1 bimestre, 1 trimestre, 1 semestre, 1 ano; usuário pode escolher qualquer valor entre 1 dia e 1 ano.

### 4.4 Entrada por voz em todos os chats
- Em todas as telas de chat, exibir **ícone de microfone** à direita do campo de entrada para permitir fala em vez de digitação.
- O sistema deve interpretar comandos de voz em linguagem natural da mesma forma que interpreta mensagens escritas.

## 5. Funcionalidades e requisitos (resumo)

### 5.1 Funcionalidades-chave
- Registro por chat em linguagem natural (texto e voz).
- Categorização automática via NLP e recategorização manual.
- Adição/remoção de categorias personalizadas com ícones quadrados.
- Criação de categorias com ícone padrão e opção de alterar imagem via busca na internet ou upload do aparelho/computador, com controles de segurança e direitos.
- Definição de metas com cálculo de aporte mensal e gráfico de progresso.
- Relatórios em blocos com gráficos de barras e pizza; legendas textuais.
- Controle deslizante (slice) para período entre 1 dia e 1 ano, com pontos sensíveis.
- Interação com gráficos por voz, texto ou toque.

### 5.2 Requisitos não funcionais
- Design universal: contraste, tipografia legível, botões grandes, ícones universais, alternativas textuais para gráficos.
- Compatibilidade com leitores de tela.
- Performance: resposta do chat < 2s para ações comuns; carregamento do dashboard < 1,5s em conexões móveis médias.
- Segurança e privacidade: criptografia em trânsito e repouso; consentimento explícito para uso de voz; anonimização para análises agregadas.
- Portabilidade: app responsivo para diferentes tamanhos de tela.
- Telemetria e logging para análise de falhas de NLP e comportamento do slice.
- Controle de versão e rollback para ícones e categorias personalizadas.
- Regras e filtros para busca de imagens externas; orientação sobre direitos autorais; opção por biblioteca de ícones licenciados.

## 6. Critérios de aceitação e métricas de sucesso

### 6.1 Critérios de aceitação (MVP)
- Registro de gasto por chat (texto e voz) corretamente interpretado em ≥ 90% dos casos no conjunto de testes inicial.
- Categorização automática com ≥ 85% de acurácia no teste de validação.
- Tela de seleção de categoria exibe ícones quadrados para cada categoria e permite criação/edição de categorias.
- Criação de nova categoria gera ícone padrão e permite alteração de imagem via busca na internet ou upload do aparelho/computador, com controles de segurança.
- Criação de meta calcula aporte mensal corretamente e exibe gráfico de progresso.
- Controle de tempo (slice) funcional e refletindo corretamente os dados exibidos.
- Interface com elementos de design universal implementados.

### 6.2 Métricas de sucesso iniciais
- Taxa de adoção: % de usuários que registram ao menos 5 transações no primeiro mês.
- Retenção 7/30 dias.
- Taxa de correção manual de categoria (meta: < 15%).
- Percentual de metas atingidas ou em andamento conforme aporte calculado.
- Satisfação do usuário (NPS ou CSAT) em testes de usabilidade.

## 7. Privacidade, segurança e conformidade
- Consentimento claro para gravação/uso de voz.
- Armazenamento mínimo: reter apenas dados necessários; permitir exportação e exclusão de dados pelo usuário.
- Autenticação: suporte a biometria e PIN.
- Conformidade: considerar LGPD (Brasil) e boas práticas de proteção de dados.
- Política de retenção de dados a definir (ex.: 2 anos por padrão, com opção de exclusão).
- Regras para uso de imagens externas: filtros de conteúdo, verificação de licenças e orientação ao usuário sobre direitos autorais.

## 8. Riscos, mitigação e dependências

### 8.1 Riscos principais
- NLP/ASR falha em interpretar entradas ambíguas.
  - Mitigação: fluxo de confirmação; exemplos de entrada; fallback para perguntas de esclarecimento; logs para melhorar modelos.
- Problemas de acessibilidade em dispositivos variados.
  - Mitigação: testes com leitores de tela; seguir guidelines WCAG; testes com usuários reais.
- Uso indevido de imagens ao permitir busca na internet para ícones.
  - Mitigação: aplicar filtros de conteúdo; orientar sobre direitos autorais; oferecer biblioteca de ícones licenciados; permitir upload local com validação.
- Privacidade e confiança do usuário com dados financeiros.
  - Mitigação: transparência, criptografia, políticas claras e controles de exclusão.

### 8.2 Dependências técnicas
- Serviço de NLP/ASR confiável.
- Backend e banco de dados.
- Frameworks de UI acessíveis.
- Infraestrutura para criptografia, telemetria e busca segura de imagens.

## 9. Roadmap e plano de validação (sugestão)
1. Semana 0–2: protótipo de alta fidelidade no Lovable (dashboard com blocos Receitas/Despesas/Metas).
2. Semana 3–6: integração básica de NLP/ASR para registro; protótipo interativo do slice de tempo; tela de seleção de categoria com ícones e fluxo de criação.
3. Semana 7–10: testes com 10–20 usuários diversos; validar criação/edição de categorias e busca/upload de imagens; coletar erros de NLP e problemas de usabilidade.
4. Semana 11–14: ajustar modelos, implementar cálculo de aporte mensal e gráfico de metas.
5. Semana 15–20: piloto com 100 usuários; medir métricas e iterar.

## 10. Alterações e adições recomendadas (prioridade)
- Adicionar requisitos de logging e telemetria para entender falhas de NLP e comportamento do slice.
- Definir política de retenção de dados.
- Especificar formatos de exportação (CSV/JSON) se necessário.
- Detalhar testes de acessibilidade (checklist WCAG e cenários de teste com leitores de tela).
- Criar scripts de onboarding com exemplos de frases para treinar o usuário no uso do chat por voz/texto.
- Definir biblioteca inicial de ícones licenciados e regras para uso de imagens externas (filtros e atribuição).
- Implementar validação e moderação para imagens carregadas pelo usuário ou buscadas na web.

## 11. Observações de interação e usabilidade (para documentação)
- Em todas as telas de chat, exibir ícone de microfone à direita do campo de entrada para permitir fala em vez de digitação.
- Na tela de relatório por categoria (ex.: “Último mês”), o usuário pode solicitar a visualização de uma categoria por comando verbal, mensagem escrita ou toque direto no gráfico.
- Na tela de classificação do gasto, incluir botão “Registrar em Outra Categoria” para recategorização.
- Na tela inicial, permitir adicionar e excluir categorias personalizadas via botões na parte inferior.
- A tela principal deve exibir os blocos: Receitas, Despesas e Metas e os gráficos correspondentes às despesas iniciais: Transporte, Alimentação, Lazer, Vestuário, Compras.
- Cada categoria deve ser representada por um ícone quadrado com a imagem correspondente.
- Ao criar nova categoria, gerar ícone padrão e permitir alteração de imagem via busca na internet com controles de segurança e direitos, ou upload de imagem do aparelho/computador.

## 12. Próximos passos recomendados
- Incorporar alterações prioritárias ao PRD e gerar brief técnico para backend/NLP.
- Preparar protocolo de teste de usabilidade com roteiro e métricas.
- Definir biblioteca inicial de ícones licenciados e regras para busca/uso de imagens externas.
- Gerar protótipos interativos no Lovable conforme roadmap e iniciar testes com usuários reais.
'''


## Prints ou pequenos vídeos das interações com a IA;  

https://lovable.dev/projects/b9ab38aa-0273-4112-9517-4fac79b10963


<img width="506" height="867" alt="image" src="https://github.com/user-attachments/assets/d055888a-6b3e-4d94-9c1f-bf4fffb325f0" />


## resumo do que o seu **App de Finanças Pessoais** faz

Imagine um app que transforma o controle financeiro em algo simples e acessível. Com ele, você registra receitas e despesas falando ou digitando, sem planilhas complicadas. As despesas são automaticamente categorizadas em blocos visuais — transporte, alimentação, lazer, vestuário e compras — cada uma com seu ícone próprio. Você pode criar novas categorias e personalizar os ícones com imagens da internet ou do seu computador. Além disso, o app ajuda a definir metas: você escolhe o valor e o prazo, e ele calcula quanto precisa aportar por mês, mostrando seu progresso em gráficos claros e intuitivos. Tudo isso em uma interface inclusiva, com design universal, que permite interagir por voz, texto ou toque. É o seu assistente financeiro pessoal, sempre pronto para simplificar decisões e dar clareza ao seu dinheiro

## Uma breve **reflexão sobre o processo**:
  - O que funcionou bem?
    revisei várias vezes o PRD e tentei deixar o mais fidedigno possível do que imaginei para o APP, que ficou exatamente do jeito que imaginei. Assim, não precisei fazer outras interações com a ferramenta.
    
  - O que não funcionou como o esperado?
    Por enquanto nada, acho que ao testar poderia decobrir alguma funcionalidade que não está de acordo, mas por enquanto tudo 100%.
     
  - O que aprendeu sobre conversar com IAs?
    Achei que seria mais complexo, descobri que é muito simples conversar com IA e que em alguns pontos é melhor do que conversar com humanos. 


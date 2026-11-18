# COM-02 — BASE COMISSIONÁVEL E TRATAMENTO DE DESCONTOS E PROMOÇÕES

**Versão:** 1.0 — regra comercial aprovada conjuntamente / ativação condicionada  
**Data:** 2026-11-18  
**Aprovadores:** Keven e Rafael  
**Status:** APPROVED_AS_JOINT_BUSINESS_RULE / PRODUCTION_ACTIVATION_BLOCKED_PENDING_LEGAL_ACCOUNTING_PSP_REVIEW  
**Dependências:** COM-01; revisão jurídica e contábil; contrato do fornecedor; homologação do PSP  
**Documentos relacionados:**
- COMMISSION_POLICY_AND_FOUNDING_PARTNER_LAUNCH_2026-11-18.md
- MARKETPLACE_COMMERCIAL_AND_OPERATING_MODEL_PROPOSAL_2026-11-18.md
- ORDER_CONTRACT_PAYMENT_STATE_MACHINE_2026-11-18.md
- COMMERCIAL_POLICY_APPROVAL_SHEET_2026-11-18.md

> Esta política registra a decisão comercial conjunta dos responsáveis. Ela não é parecer jurídico ou contábil, não define a base tributária de qualquer parte e não autoriza cobrança em produção. A fórmula deverá ser conferida com o contrato, a emissão fiscal, a liquidação efetiva e o PSP escolhido antes da ativação financeira.

## 1. Objetivo e regra principal

Definir, de forma auditável e compreensível para o fornecedor, sobre qual valor o Yvenist calcula a comissão aprovada na COM-01.

**Regra aprovada:** a comissão incide sobre a remuneração que o fornecedor tem direito a receber pela parte efetivamente concluída do pedido, antes de descontar a comissão do Yvenist e os custos de processamento do PSP, excluindo somente valores de terceiros que sejam repasses genuínos, separados e comprovados.

A base não é automaticamente:
- o valor que o consumidor pagou no checkout;
- o preço de catálogo sem considerar as condições contratadas;
- o valor líquido depositado pelo PSP depois de suas taxas;
- o GMV total do evento com vários fornecedores.

O cálculo é feito **por fornecedor/subpedido e pelas linhas ou parcelas efetivamente concluídas**. Um fornecedor não paga comissão sobre a parte de outro fornecedor.

## 2. Conceitos simples

| Conceito | Significado para o Yvenist |
|---|---|
| Preço contratado | Valor e escopo que consumidor e fornecedor aceitaram para aquele pedido |
| Desconto financiado pelo fornecedor | Parte do desconto que reduz o valor que o fornecedor receberá; reduz a base |
| Desconto financiado pelo Yvenist/plataforma | Parte custeada pela plataforma e efetivamente compensada ao fornecedor; não reduz a remuneração do fornecedor |
| Desconto cofinanciado | Promoção dividida entre fornecedor e plataforma; somente a parcela economicamente suportada pelo fornecedor reduz sua remuneração |
| Repasse de terceiro | Valor cobrado em nome de prestador independente, separado e documentado, sem se tornar receita/remuneração do fornecedor |
| Taxa PSP | Custo de pagamento; permanece separado da comissão e não reduz automaticamente a base |
| Comissão adquirida | Comissão referente à parte concluída conforme o contrato e a regra de conclusão; pagamento aprovado, isoladamente, não prova conclusão |

**Importante:** a classificação exibida no painel de uma plataforma como “cupom da plataforma” ou “promoção patrocinada” não basta. O sistema deve identificar quem suporta economicamente o desconto e conferir se a parcela financiada pela plataforma realmente é creditada/compensada ao fornecedor. O nome da campanha não substitui a conciliação financeira.

## 3. Fórmula operacional

Para cada fornecedor e parte concluída:

**Base comissionável = remuneração devida ao fornecedor pela parte concluída − repasses comprovados a terceiros independentes.**

A remuneração do fornecedor já deve refletir:
- descontos efetivamente suportados pelo fornecedor;
- subsídios ou créditos promocionais financiados pela plataforma que preservem/complementem o valor devido ao fornecedor;
- ajustes e reembolsos que efetivamente reduzam o direito do fornecedor, conforme o contrato e a política de cancelamento/reembolso aplicável.

Para conferência de cada promoção:

**Desconto suportado pelo fornecedor = desconto total − parcela de plataforma/parceiro efetivamente creditada ou compensada ao fornecedor.**

O cálculo definitivo deve usar valores monetários em centavos inteiros (BRL), sem ponto flutuante.

### 3.1. Descontos financiados pelo fornecedor

Reduzem a base porque o fornecedor abriu mão daquela parte do preço.

Exemplos:
- desconto percentual criado pelo fornecedor;
- cupom próprio do fornecedor;
- redução de preço para campanha assumida pelo fornecedor;
- desconto por quantidade, pacote ou negociação custeado pelo fornecedor;
- parcela do fornecedor em cupom cofinanciado;
- desconto no frete ou adicional quando esse custo seria remuneração do próprio fornecedor.

### 3.2. Descontos financiados pelo Yvenist ou pela plataforma

Não reduzem a base **na parcela efetivamente suportada pela plataforma e creditada/compensada ao fornecedor**, porque o fornecedor continua tendo direito à remuneração contratada.

Exemplo: preço contratado de R$ 1.000; o Yvenist oferece cupom de R$ 100 custeado pela plataforma; o consumidor paga R$ 900 e o fornecedor recebe/tem direito a R$ 1.000 antes da comissão e do PSP. A base é R$ 1.000. Na taxa de 3%, a comissão ilustrativa é R$ 30.

Se a plataforma apenas reduz o preço pago pelo consumidor, mas não compensa o fornecedor, a parte não compensada reduz a remuneração do fornecedor. Ela não pode ser tratada como subsídio financiado pela plataforma apenas por causa do nome ou da etiqueta da campanha.

### 3.3. Descontos cofinanciados

Quando fornecedor e plataforma dividem o custo, a base considera a parcela que permanece devida ao fornecedor depois da contribuição dele. A parcela da plataforma só preserva a remuneração na medida em que seja efetivamente custeada/creditada pela plataforma.

Exemplo didático: preço contratado de R$ 1.000; cupom total de R$ 100; fornecedor financia R$ 50 e Yvenist financia/compensa os outros R$ 50. O consumidor paga R$ 900; a remuneração do fornecedor antes de comissão e taxa PSP é R$ 950. A base é R$ 950; a 3%, a comissão é R$ 28,50.

A proporção de cofinanciamento deve ser aceita e registrada antes de a campanha começar. Não presumir divisão 50/50.

### 3.4. Desconto de banco, cartão ou parceiro externo

Identificar quem absorve o custo e o que o fornecedor efetivamente recebe:
- se banco/emissor/parceiro paga ou credita a diferença ao fornecedor e preserva a remuneração, a diferença não reduz a base;
- se o fornecedor absorve o desconto, ele reduz a base;
- se a plataforma absorve o desconto sem repassar/compensar o fornecedor, a remuneração efetiva é menor e a base acompanha esse valor.

Registrar a origem e o valor em separado. Não classificar automaticamente todo desconto de pagamento como desconto do Yvenist.

## 4. Exemplos numéricos de referência

Os exemplos usam comissão de 3% somente para ilustrar a base; a taxa efetiva do fornecedor continua vinculada à COM-01 e ao snapshot aceito.

| Cenário | Preço/valor original | Desconto total | Parcela suportada pelo fornecedor | Parcela compensada pela plataforma | Base ilustrativa | Comissão a 3% |
|---|---:|---:|---:|---:|---:|---:|
| Sem promoção | R$ 1.000,00 | R$ 0,00 | R$ 0,00 | R$ 0,00 | R$ 1.000,00 | R$ 30,00 |
| Cupom do fornecedor | R$ 1.000,00 | R$ 100,00 | R$ 100,00 | R$ 0,00 | R$ 900,00 | R$ 27,00 |
| Cupom do Yvenist, fornecedor preservado | R$ 1.000,00 | R$ 100,00 | R$ 0,00 | R$ 100,00 | R$ 1.000,00 | R$ 30,00 |
| Cupom cofinanciado 50/50 | R$ 1.000,00 | R$ 100,00 | R$ 50,00 | R$ 50,00 | R$ 950,00 | R$ 28,50 |
| Campanha marcada como “plataforma”, mas sem compensação ao fornecedor | R$ 1.000,00 | R$ 100,00 | R$ 100,00 de redução econômica | R$ 0,00 | R$ 900,00 | R$ 27,00 |

Valores antes de taxa PSP e eventuais tributos/ajustes. O exemplo não representa promessa de repasse líquido.

## 5. O que entra e o que fica separado

### 5.1. Incluído na remuneração do fornecedor

Quando compuser o preço contratado do próprio fornecedor e a parte tiver sido concluída:
- produtos, kits e itens vendidos pelo fornecedor;
- prestação de serviço do próprio fornecedor;
- adicionais e opcionais aceitos pelo consumidor;
- entrega realizada pelo próprio fornecedor;
- montagem, instalação, deslocamento, visita técnica ou mão de obra do próprio fornecedor;
- taxas acessórias que constituam remuneração do próprio fornecedor e tenham sido informadas/aceitas.

### 5.2. Terceiros independentes

Um valor só pode ser retirado como repasse comprovado a terceiro quando todos os requisitos forem atendidos:
1. o terceiro é independente e identificável;
2. o valor é discriminado separadamente antes da contratação;
3. existe documento/recibo ou evidência compatível do valor;
4. o fornecedor atua como mero repassador daquele valor, sem margem ou remuneração embutida;
5. a responsabilidade e o fluxo financeiro estão descritos no contrato.

Se o fornecedor acrescentar margem, taxa de gestão ou remuneração própria, essa parcela integra sua remuneração comissionável. Não excluir custo de terceiro apenas porque o fornecedor o chama de “despesa”.

### 5.3. Taxa do PSP

A taxa do PSP fica fora da fórmula da base e deve ser exibida como custo independente. Ela não pode ser abatida silenciosamente da base comissionável. Quem suporta economicamente essa taxa é a decisão COM-03, ainda pendente.

### 5.4. Tributos

Não aplicar exclusão automática de ISS, ICMS, IBS/CBS, retenções ou qualquer outro tributo da base comercial. O tratamento fiscal depende do papel contratual, do documento fiscal, do regime e da operação. A base comercial aprovada nesta COM-02 não é, por si só, a base de cálculo de tributos do fornecedor ou do Yvenist. Qualquer tratamento específico exige validação do contador/tributarista e, se necessário, do advogado, antes de produção.

### 5.5. Gorjetas e valores voluntários

Gorjetas genuinamente voluntárias, destacadas do preço e sem integração à remuneração contratada do fornecedor, ficam fora da base. Não chamar de gorjeta uma taxa obrigatória ou valor necessário para executar o serviço.

## 6. Descontos em carrinho, pacotes e Party Maker

- Toda promoção deve indicar quem a financia, seu valor total, a parcela de cada financiador, os produtos/serviços elegíveis, vigência, limites e regras de acumulação.
- Aplicar a apuração por fornecedor. Um desconto suportado por um fornecedor não pode ser distribuído para reduzir a base de outro fornecedor.
- Desconto fixo de carrinho que envolva várias linhas deve ser alocado apenas às linhas elegíveis, dentro de cada subpedido, segundo regra determinística e apresentada antes da contratação. Recomenda-se rateio proporcional ao valor elegível de cada linha antes do desconto, com ajuste de centavos por método determinístico.
- Quando houver promoção cofinanciada, separar as cotas de financiamento na alocação de cada linha.
- Desconto em pacote/kits, compre mais/pague menos, brinde ou produto gratuito deve gerar uma composição monetária explícita no snapshot. Não criar cobrança de comissão sobre valor fictício nem atribuir desconto silenciosamente a linhas não elegíveis.
- No Party Maker, manter EventRequest como visão consolidada e calcular cada SupplierSubOrder isoladamente.
- Na compra imediata, aplicar a mesma regra por SupplierSubOrder, ainda que a experiência do consumidor seja um checkout único.
- A ordem de acumulação de cupons e descontos precisa ser informada ao fornecedor e congelada no snapshot do pedido. Não presumir que todos os cupons são cumulativos.

## 7. Cancelamentos, conclusão e reembolsos

A base é apurada apenas sobre a parte efetivamente concluída. Se uma linha/parte não foi executada ou a remuneração do fornecedor foi efetivamente reduzida por cancelamento/reembolso, o valor correspondente não integra ou deve ser retirado da base.

Em caso de execução parcial, identificar a parcela que foi efetivamente entregue/prestada e aceita como concluída segundo o contrato. Em caso de disputa, manter a parcela contestada em estado pendente até decisão aplicável.

A COM-02 define o efeito econômico na base; **não aprova por si só prazos, multas ou a política completa de cancelamento/reembolso**. A decisão detalhada de comissão em reembolso parcial continua vinculada à COM-04 e à revisão jurídica/contábil.

Chargeback deve permanecer como evento financeiro/disputa separado. Só ajustar a base de modo definitivo quando o resultado do chargeback/reversão efetivamente alterar a remuneração do fornecedor, preservando trilha de auditoria.

## 8. Registros obrigatórios e implementação

O sistema deve permitir reconstruir a base de cada comissão a partir de registros imutáveis/versionados.

### 8.1. Promoção e financiamento

Guardar por campanha/aplicação:
- identificador, tipo e código/nome interno;
- financiador(es): fornecedor, Yvenist, parceiro de pagamento ou cofinanciado;
- valor total do desconto;
- parcelas efetivamente suportadas por cada parte;
- regras de elegibilidade, limite, vigência e acumulação;
- fornecedor, linhas/subpedido elegíveis e critérios de alocação;
- aceite do fornecedor e versão dos termos da campanha;
- evidência de compensação/subsídio ao fornecedor, quando houver.

### 8.2. Alocação por linha

Guardar por linha do SupplierSubOrder:
- valor contratado antes de promoções;
- descontos alocados por campanha e fonte de financiamento;
- desconto efetivamente suportado pelo fornecedor;
- desconto financiado/compensado pela plataforma;
- desconto financiado/compensado por parceiro de pagamento;
- valor de terceiros documentado e referência da evidência;
- quantidade/valor concluído;
- valor efetivamente reembolsado/revertido que reduza a remuneração do fornecedor;
- valor de remuneração do fornecedor antes de comissão Yvenist e taxa PSP;
- base comissionável final em centavos.

### 8.3. Snapshot da comissão

CommissionEntry deve guardar, no mínimo:
- identificador do subpedido e linhas de origem;
- versão da política de comissão e taxa aplicada;
- base comissionável em centavos;
- memória de cálculo (remuneração concluída, descontos suportados pelo fornecedor, subsídios creditados, reembolsos/reversões e repasses de terceiros);
- valor da comissão, moeda e método de arredondamento;
- evento/prova de conclusão;
- timestamps, ator e referências dos registros de promoção, contrato, pagamento e reembolso.

Recalcular não significa sobrescrever: criar ajuste/reversão vinculado ao cálculo original, com motivo e trilha de auditoria.

### 8.4. Controles obrigatórios

- Usar centavos inteiros para BRL; nunca float/ponto flutuante para dinheiro.
- Congelar preço, promoção, financiador, alocação, taxa e base no snapshot contratual.
- Alteração de promoção após aceite exige nova versão e consentimento quando alterar preço, remuneração ou condição do fornecedor/consumidor.
- A tela do fornecedor deve mostrar preço, desconto do fornecedor, subsídio da plataforma, base comissionável, taxa da COM-01, comissão estimada, taxa PSP separada e líquido estimado.
- Não calcular comissão por GMV global do evento.
- Não marcar comissão como adquirida apenas porque o pagamento foi aprovado; a conclusão é condição separada.
- Exigir reconciliação com o extrato/relatório do PSP antes da liquidação contábil.
- Logs de campanha, cálculo, aceite e ajuste devem ser acessíveis para auditoria e suporte.

## 9. Critérios de aceite para Claude Code

Claude Code pode implementar a regra somente após receber esta versão aprovada e os contratos/pareceres aplicáveis. Os testes mínimos devem cobrir:
1. preço sem desconto;
2. cupom integralmente financiado pelo fornecedor;
3. cupom integralmente financiado pelo Yvenist com remuneração do fornecedor preservada;
4. cupom cofinanciado em proporções variadas;
5. campanha rotulada como plataforma sem crédito efetivo ao fornecedor;
6. cupom de banco/cartão/parceiro e respectiva fonte econômica;
7. desconto fixo distribuído entre linhas de um mesmo subpedido;
8. Party Maker com múltiplos fornecedores, sem transferência de desconto entre eles;
9. pacote, quantidade, brinde e item gratuito;
10. entrega/montagem do próprio fornecedor versus repasse documentado a terceiro;
11. reembolso total/parcial e prestação parcialmente concluída;
12. arredondamento de centavos, idempotência e reversões auditáveis;
13. congelamento da política/taxa/base no snapshot e proibição de retroatividade.

## 10. Limites e dependências antes de produção

Permanecem obrigatórios:
- revisão por contador/tributarista brasileiro da base contratual, documentos fiscais, tributos, descontos e repasses;
- revisão por advogado brasileiro do contrato de fornecedor, informação pré-contratual, publicidade de promoções, termos de comissão, reembolso e responsabilidade;
- confirmação do PSP sobre tratamento de cupons/subsídios, split, relatórios, estornos, chargebacks e conciliação;
- validação de sandbox com casos de desconto financiado, cofinanciado, reembolso parcial e múltiplos fornecedores.

A aprovação da COM-02 é uma **decisão comercial interna de trabalho**. Ela não autoriza transações reais nem substitui validação especializada.

## 11. Pesquisa externa e decisões que ela informa

A pesquisa comparou mecanismos e documentação de marketplaces. Os exemplos demonstram práticas úteis de rastreabilidade, não uma regra universal nem taxas para copiar.

- **TikTok Shop Brasil — Co-funded Campaign:** documentação para o Brasil descreve cupons cofinanciados, proporção de contribuição de plataforma e seller, repasse da parcela da plataforma ao vendedor e detalhamento das parcelas promocionais no pedido. A página informa atualização em 02/10/2026. Lição aplicada: registrar o valor financiado por cada parte e conferir a compensação ao seller.  
  https://seller-br.tiktok.com/university/essay?knowledge_id=2569565069149953&lang=en
- **Mercado Livre Developers — Gerenciar promoções:** diferencia campanhas do vendedor, campanhas cofinanciadas e promoções com bonificação do marketplace; documenta campos separados para descontos/bonificações e rastreabilidade. Lição aplicada: não tratar toda promoção como um único abatimento sem fonte.  
  https://developers.mercadolivre.com.br/pt_br/gerenciar-ofertas
- **Mercado Livre Developers — Cupons do vendedor:** descreve campanhas de cupons criadas pelo vendedor e tipos de desconto por valor fixo ou percentual. Lição aplicada: distinguir cupom criado/financiado pelo seller de campanha financiada pela plataforma.  
  https://developers.mercadolivre.com.br/pt_br/produto-consulta-de-usuarios/cupons-do-vendedor
- **Amazon Seller Central Brasil — Discounts Provided by Amazon:** a documentação informa que, em descontos financiados pela Amazon, o vendedor recebe o preço cheio definido e a taxa de referência é calculada sobre esse preço. Lição aplicada: subsídio da plataforma não deve reduzir a base quando preserva a remuneração do seller.  
  https://sellercentral.amazon.com.br/help/hub/reference/external/G202170300
- **Amazon Seller Central Brasil — Referral fees for orders with promotions:** a documentação descreve cálculo de referral fee sobre o preço de venda após a promoção para pedidos com promoção. Lição aplicada: quando o desconto reduz o preço de venda aplicável, a base/fee segue o preço promocional previsto nos termos daquele programa.  
  https://sellercentral.amazon.com.br/help/hub/reference/external/G202134700

As documentações variam por produto, campanha, contrato, região e tipo de vendedor. Nenhuma delas determina a fórmula do Yvenist. A política Yvenist foi escolhida para vincular a comissão à remuneração efetiva do fornecedor e identificar a parte que suportou cada desconto.

## 12. Registro de aprovação

- COM-02 — base por fornecedor/subpedido e parte concluída, vinculada à remuneração efetiva do fornecedor antes da comissão Yvenist e da taxa PSP: **APROVADA CONJUNTAMENTE — 2026-11-18**.
- Tratamento de desconto do fornecedor, desconto de plataforma, cofinanciamento e terceiros conforme esta versão 1.0: **APROVADO COMO REGRA COMERCIAL INTERNA — 2026-11-18**.
- Exclusão automática de tributos: **NÃO APROVADA / NÃO PERMITIDA** sem parecer especializado.
- Alocação de taxa PSP: **COM-03 PENDENTE**.
- Regra detalhada de reembolso/cancelamento: **COM-04 E POLÍTICAS OPERACIONAIS PENDENTES**.
- Ativação financeira em produção: **BLOQUEADA** até parecer jurídico/contábil e homologação do PSP.

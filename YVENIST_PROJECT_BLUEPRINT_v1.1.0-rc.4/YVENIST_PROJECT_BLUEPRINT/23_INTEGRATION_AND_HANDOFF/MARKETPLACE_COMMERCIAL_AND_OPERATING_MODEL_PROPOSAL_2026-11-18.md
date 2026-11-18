# MODELO COMERCIAL E OPERACIONAL DO MARKETPLACE — PROPOSTA v0.4

**Data:** 2026-11-18  
**Status:** PROPOSTA ESTRUTURADA / AGUARDANDO APROVAÇÃO CONJUNTA E REVISÃO ESPECIALIZADA  
**Decisões de origem:** respostas conjuntas de Keven e Rafael registradas em 2026-11-18  
**Documento relacionado:** `ORDER_CONTRACT_PAYMENT_STATE_MACHINE_2026-11-18.md`

> Este documento transforma as direções dos responsáveis em um modelo operacional recomendado. A comissão sugerida, as políticas de cancelamento, os prazos e os meios de pagamento abaixo ainda não são decisões aprovadas. Não devem ser publicados como termos finais nem implementados como política comercial definitiva antes da aprovação de ambos e das revisões jurídica, contábil e do provedor de pagamentos.

## 1. Resumo executivo

O modelo inicial do Yvenist deve combinar três fontes de receita, em momentos diferentes:

1. **Comissão por contratação concluída:** receita principal, cobrada do fornecedor conforme percentual acordado e calculada sobre a parte elegível efetivamente concluída.
2. **Exposição patrocinada no Explorar contextual:** receita adicional de fornecedores que pagam para ocupar espaços identificados como patrocinados. A relevância e a elegibilidade vêm antes da venda de posição.
3. **Plano de assinatura do consumidor:** direção futura, fora do escopo comercial inicial até que benefícios, preço, capacidade operacional e condições sejam definidos.

A operação deve manter dois tipos de jornada:

- **Party Maker:** um pedido do consumidor para organizar um evento, contendo subpedidos individuais por fornecedor. Cada fornecedor confirma ou recusa a própria parte.
- **Compra imediata:** sacola/carrinho e checkout para produtos, kits ou serviços independentes, sem obrigar a criação de uma festa.

O Yvenist deve oferecer uma experiência unificada, mas manter separado o registro comercial, financeiro e contratual de cada fornecedor. O total do evento pode ser agregado para o consumidor; a prestação, a resposta, a comissão, o pagamento, o repasse e eventual reembolso devem ser rastreáveis por subpedido.

## 2. Referências externas e o que podemos aprender

As referências servem para entender mecanismos, não para copiar percentuais ou obrigações.

### 2.1. iFood

A página pública do iFood para restaurantes apresenta planos com comissões diferentes conforme o serviço oferecido. Na página consultada, o Plano Básico indica comissão de 12% sobre pedidos delivery e taxa de 3,2% para pagamentos realizados pelo iFood; o plano com entrega da plataforma indica comissão de 23%, além da taxa de pagamento. Isso demonstra que o preço do marketplace pode distinguir comissão, processamento de pagamento e serviços operacionais incluídos. O Yvenist não deve aplicar automaticamente a taxa maior, pois não está oferecendo a mesma estrutura de entrega/logística.  
Referências:  
- https://parceiros.ifood.com.br/restaurante/planos-ifood  
- https://parceiros.ifood.com.br/restaurante/como-funciona/entregas  
- https://parceiros.ifood.com.br/restaurante/como-funciona/pagamento

A política pública de cancelamento do iFood diferencia momentos do pedido, como antes da confirmação pela loja e etapas posteriores de preparo/entrega. A lição para o Yvenist é modelar cancelamentos por estado operacional, em vez de apresentar uma regra universal.  
Referência: https://institucional.ifood.com.br/clientes/cancelar-pedido-cliente-restaurante-faq/

### 2.2. Airbnb

O artigo do Airbnb publicado em 13 de outubro de 2026 informa taxa única de serviço de 15,5% paga pelo anfitrião em sua estrutura geral, com exceções de 16% para anúncios no Brasil e México, e descreve a dedução da taxa do valor do anfitrião. A plataforma também publica regras específicas para cancelamentos de serviços e experiências por anfitriões, com consequências previstas para cancelamentos sem justificativa válida.  
Referências:
- https://www.airbnb.com.br/resources/hosting-homes/a/how-much-does-airbnb-charge-hosts-288
- https://www.airbnb.com.br/help/article/2039
- https://www.airbnb.com.br/help/article/2278

O Yvenist pode aprender com transparência de taxas, regras específicas por tipo de serviço, incentivos de confiabilidade e tratamento documentado de exceções. Não deve adotar automaticamente a taxa de 16% ou a penalidade de 20% do Airbnb: são condições de outro produto, contrato e operação.

## 3. Modelo de receita recomendado

### 3.1. Comissão por contratação

**Proposta de comissão progressiva híbrida:** 3% para Parceiros Fundadores durante a fase de lançamento; 5% na fase de expansão; 10% como taxa-alvo de maturidade. A comissão é paga pelo fornecedor e calculada por subpedido sobre a base comissionável da parte efetivamente concluída.

A taxa de 3% é uma condição de aquisição de oferta para a coorte inicial, não uma promessa de taxa permanente nem uma taxa universal para todo fornecedor futuro. A progressão não deve ocorrer por calendário isolado. A passagem a 5% e depois a 10% depende de critérios de maturidade, comunicação antecipada, aceite contratual e decisão conjunta dos sócios. Até que os critérios sejam aprovados, nenhuma mudança automática de taxa deve ser ativada.

Exemplo ilustrativo para subpedido concluído de R$ 1.000,00: a 3%, comissão de R$ 30,00 e saldo de R$ 970,00; a 5%, R$ 50,00 e R$ 950,00; a 10%, R$ 100,00 e R$ 900,00. Valores antes de PSP, tributos, ajustes, reembolsos e custos atribuídos em contrato.

A comissão é apurada por fornecedor. Um evento com quatro fornecedores terá quatro bases e quatro apurações independentes, não uma comissão indistinta sobre todo o evento. A política detalhada está em `COMMISSION_POLICY_AND_FOUNDING_PARTNER_LAUNCH_2026-11-18.md`.

### 3.2. Base de cálculo recomendada

Criar uma definição técnica chamada `commissionable_amount`, calculada a partir das linhas do subpedido:

- incluir preço dos itens/serviços e adicionais efetivamente contratados e concluídos;
- considerar descontos financiados pelo próprio fornecedor na base líquida após o desconto;
- excluir itens cancelados e valores efetivamente reembolsados;
- tratar separadamente frete, deslocamento, montagem, tributos, gorjetas, descontos financiados pelo Yvenist e valores de terceiros;
- não presumir que tributos ou despesas acessórias podem ser excluídos da base sem validação contábil e jurídica.

A definição final deve refletir quem vende, quem emite documento fiscal, quem recebe o pagamento e como o contrato descreve a comissão. Registrar essa base no contrato do fornecedor e na configuração de cada versão da política.

### 3.3. Quando a comissão é gerada

Recomendação:
- no pagamento aprovado, registrar a comissão prevista como `pending_completion`;
- após a conclusão comprovada da parte contratada, marcar a comissão elegível como `earned`;
- em cancelamento ou reembolso parcial, recalcular/reverter proporcionalmente a comissão da parcela afetada;
- em chargeback, registrar exposição financeira e seguir o contrato com PSP/fornecedor;
- nunca considerar uma mera solicitação de orçamento ou resposta positiva do fornecedor como contratação concluída.

Se o PSP deduzir a comissão no momento do pagamento, a escrituração interna ainda deve distinguir comissão calculada, comissão adquirida, reversão e valor a liquidar. A mecânica financeira do PSP e o reconhecimento contábil não são a mesma coisa.

### 3.4. Taxa do provedor de pagamento

A taxa do PSP deve aparecer como custo separado da comissão do Yvenist.

Proposta inicial:
- não esconder a taxa do PSP dentro da comissão;
- não transferir uma taxa adicional ao consumidor sem decisão conjunta e informação prévia;
- comparar cenários em que o custo é absorvido pelo Yvenist ou deduzido do recebível do fornecedor;
- mostrar ao fornecedor o valor bruto, comissão, custo de pagamento, ajustes e líquido estimado antes de aderir e sempre que fizer uma contratação.

A política definitiva precisa ser aprovada pelos dois responsáveis. A ordem de cálculo pode variar conforme o contrato e a implementação do PSP. Por exemplo, a documentação do Mercado Pago informa que, no split 1:1 documentado, a taxa do Mercado Pago é descontada antes da comissão do marketplace. Não codificar uma fórmula universal sem validar o PSP escolhido.

### 3.5. Regras para reembolso e comissão

- Cancelamento integral antes de qualquer prestação: comissão adquirida igual a zero; reverter valores ainda não adquiridos.
- Reembolso parcial: recalcular a comissão sobre a parcela efetivamente mantida e concluída.
- Serviço parcialmente executado: somente a parte considerada concluída segundo critérios previamente contratados pode gerar comissão; casos disputados ficam pendentes.
- Chargeback: manter registro separado e não mascarar perda como cancelamento comum.
- Descontos promocionais: identificar quem financiou o desconto e como ele afeta a base.

## 4. Exposição patrocinada no Explorar

Os responsáveis aprovaram a direção de vender exposição prioritária na área contextual do Explorar, exibida após a criação de uma festa.

Regras recomendadas:

1. A etiqueta **Patrocinado** ou **Destaque pago** deve aparecer de modo perceptível.
2. A compra de exposição não altera nota, quantidade de avaliações, selo de verificação ou qualidade real do fornecedor.
3. Primeiro aplicar critérios mínimos de elegibilidade: categoria, localidade, data, capacidade, tipo de evento, serviço ofertado e disponibilidade.
4. Somente entre os elegíveis distribuir as posições patrocinadas.
5. Manter recomendações orgânicas identificáveis e não misturar pagamento com afirmações como “mais bem avaliado”.
6. Medir separadamente impressões, cliques, conversão, cancelamentos, reclamações e conclusão de fornecedores patrocinados e orgânicos.
7. A taxa de exposição é independente da comissão por contratação; deixar isso claro no painel do fornecedor.

**Proposta de início:** inventário pequeno de posições patrocinadas e preço por campanha/região/categoria, sem leilão complexo. Preço, quantidade de posições, duração e política de elegibilidade exigem aprovação conjunta.

## 5. Assinatura do consumidor — fase futura

A assinatura é uma direção futura, não uma promessa do MVP.

Benefícios possíveis para pesquisa e validação:
- ferramentas avançadas de planejamento e orçamento;
- modelos de festas e reutilização de listas;
- benefícios/condições especiais financiados por parceiros;
- suporte prioritário em horários e escopo definidos;
- acesso antecipado a ofertas selecionadas.

**Prioridade de agendamento** só pode ser anunciada para horários/capacidade expressamente acordados com fornecedores parceiros. Não prometer ultrapassar clientes já confirmados ou garantir vaga sem disponibilidade. A assinatura deve ter preço, renovação, cancelamento, benefícios, limitações e cobrança recorrente transparentes.

## 6. Papéis e relação contratual

Modelo de produto recomendado, sujeito a parecer jurídico:

- **Consumidor:** solicita e contrata produtos/serviços.
- **Fornecedor:** cadastra ofertas, define preços, confirma disponibilidade, executa a prestação, responde por suas obrigações e recebe o valor devido.
- **Yvenist:** opera o marketplace, catálogo, descoberta, pedido, comunicação, suporte, regras de plataforma e integração com PSP, recebendo a comissão e receitas de divulgação conforme contratos.

A qualificação jurídica do Yvenist não deve ser presumida apenas pelo rótulo “marketplace”. A forma de exibição, cobrança, recebimento, repasse, emissão fiscal, suporte e responsabilidade pode alterar a análise. Antes de transações reais, advogado brasileiro deve revisar a estrutura contratual e o papel do Yvenist em cada fluxo.

### 6.1. Cadastro e habilitação do fornecedor

Antes de aceitar pedidos pagos, exigir conforme categoria e análise de risco:
- identidade e dados cadastrais do responsável;
- dados empresariais/fiscais necessários;
- conta de recebimento e vinculação OAuth/PSP quando aplicável;
- categorias e área atendida;
- documentos/licenças exigidos para a atividade específica, quando aplicáveis;
- catálogo, preço, conteúdo incluso/excluído, disponibilidade e condições de cancelamento;
- aceite dos termos de fornecedor, comissão, pagamento e política de atendimento.

A aprovação do cadastro no Yvenist não substitui licenças profissionais, sanitárias, municipais ou outras exigências da atividade do fornecedor.

## 7. Pedido de evento e subpedidos

### 7.1. Uma solicitação do consumidor, várias relações comerciais

Quando o consumidor envia o Party Maker:
- o Yvenist cria um `EventRequest`;
- agrupa linhas por fornecedor em `SupplierSubOrder`;
- registra um snapshot de preço, data, endereço/área, evento, convidados e configurações;
- notifica cada fornecedor apenas sobre seu subpedido;
- cada fornecedor responde independentemente.

O total consolidado é uma visão para o consumidor. Não transforma os vários fornecedores em uma única empresa nem cria uma única obrigação indivisível.

### 7.2. Resposta do fornecedor

O fornecedor pode:
- **Confirmar como solicitado:** confirma capacidade, data, escopo e preço do snapshot.
- **Recusar:** informa motivo e a parte fica indisponível.
- **Solicitar alteração:** propõe mudança de data, preço, escopo ou condição. O subpedido aguarda consentimento do consumidor sobre a alteração material.

A resposta positiva autoriza a etapa seguinte de checkout. Proposta operacional: manter a disponibilidade temporariamente reservada durante uma janela de pagamento; o prazo é configurável por categoria e ainda precisa ser aprovado. A contratação definitiva ocorre somente depois da confirmação do pagamento/condição financeira e da emissão do registro contratual. Caso o pagamento não seja concluído dentro da janela, liberar a reserva temporária e avisar as partes.

### 7.3. Aceitação parcial

Um fornecedor pode recusar enquanto outros confirmam. O Yvenist não deve:
- confirmar silenciosamente um evento incompleto;
- cobrar por serviço recusado;
- cancelar automaticamente subpedidos independentes que foram aceitos.

A tela deve explicar o que foi confirmado, recusado e ainda pendente. Quando a combinação alterada afetar a viabilidade do evento (por exemplo, salão sem buffet necessário), solicitar escolha do consumidor: substituir, remover ou aguardar, conforme a dependência. O pagamento deve abranger somente os subpedidos que o consumidor escolheu contratar e que estejam confirmados.

## 8. Compra imediata e checkout

A compra imediata tem um carrinho próprio, separado do Party Maker.

Proposta de regras:
- a sacola reúne produtos/kits e serviços compráveis sem criar evento;
- agrupar linhas por fornecedor e modalidade de entrega/retirada;
- preço, quantidade, disponibilidade, prazo e taxa de entrega devem ser revalidados antes de cobrar;
- qualquer item indisponível é removido ou corrigido com consentimento, nunca cobrado silenciosamente;
- checkout pode ter uma única revisão/ação do consumidor, mas internamente pode gerar múltiplos pagamentos vinculados a subpedidos caso o PSP não suporte split com vários vendedores;
- confirmação V1 só aparece após confirmação de pagamento pelo servidor/PSP;
- o consumidor acompanha o pedido e aciona suporte no próprio pedido.

Para reduzir risco no primeiro lançamento, pode-se limitar o primeiro corte a uma combinação operacional controlada (por exemplo, um fornecedor por checkout) sem excluir do modelo de dados a futura composição multi-fornecedor. Qualquer limitação dessa primeira versão deve aparecer como recorte de entrega, e não como supressão silenciosa do escopo aprovado.

## 9. Pagamentos, split e repasses

### 9.1. Princípio de arquitetura

Usar PSP que ofereça produto marketplace, onboarding de vendedores, split/recebedores, reembolsos parciais, webhooks, conciliação e relatórios. Preferir liquidação direta aos fornecedores e retenção/dedução da comissão pelo PSP, em vez de criar uma carteira própria ou movimentar dinheiro manualmente.

O Banco Central explica que marketplaces que recebem valores de compradores e repassam a vendedores participam do fluxo financeiro; a estrutura pode caracterizar atividade de subcredenciamento e atrair regras do arranjo de pagamento. Essa análise deve ser feita com PSP e assessor jurídico/regulatório antes do desenho de produção.  
Referência: https://www.bcb.gov.br/detalhenoticia/143/noticia

### 9.2. Limitação importante para múltiplos fornecedores

A documentação consultada do Mercado Pago descreve o split 1:1 entre vendedor e marketplace e afirma que o split 1:N depende de carteira assessorada/contato comercial. O split 1:1 também envolve conta de vendedor com KYC exigido e OAuth para vinculação. Portanto, não presumir que um único pagamento será automaticamente dividido entre todos os fornecedores do Party Maker.

Referências técnicas:
- https://www.mercadopago.com.br/developers/pt/docs/split-payments/split-1-1/overview
- https://www.mercadopago.com.br/developers/pt/docs/split-payments/split-1-1/prerequisites
- https://www.mercadopago.com.br/developers/pt/docs/split-payments/split-1-1/integration-configuration/integrate-marketplace
- https://developer.pagbank.com.br/v1/reference/split-estrutura

A arquitetura Yvenist deve suportar dois caminhos sem alterar a experiência essencial:
1. **Split nativo:** um pagamento/sessão, quando PSP contratado suportar divisão entre todos os recebedores e reembolsos proporcionais.
2. **Pagamentos vinculados por subpedido:** uma revisão/checkout para o consumidor cria pagamentos individuais correlacionados por um `PaymentGroup`, se split 1:N não estiver disponível.

O consumidor deve conseguir entender o total, os fornecedores e a situação de pagamento. Cada cobrança, estorno e repasse permanece associada ao fornecedor correto.

### 9.3. Formas e agenda de pagamento

Proposta de domínio:
- compra imediata: pagamento integral no checkout como caminho padrão;
- evento agendado: suportar termos `FULL_PREPAYMENT` ou `DEPOSIT_PLUS_BALANCE`, se o PSP, categoria, fornecedor e contrato permitirem;
- depósito, saldo, vencimentos, parcelamento e gatilhos devem ser explícitos antes do consumidor contratar.

**Não definir neste momento um percentual fixo de sinal.** Os responsáveis ainda precisam escolher a regra comercial. Fornecedor não pode mudar unilateralmente cronograma ou valor depois da contratação. Se houver parcela futura, o sistema registra vencimento, notifica, acompanha falha e aplica as regras contratuais aprovadas.

### 9.4. Repasse ao fornecedor

Recomendação:
- acompanhar o valor bruto recebido, taxas PSP, comissão, estornos, ajustes e líquido previsto;
- usar o mecanismo de split/settlement do PSP;
- liberar repasse conforme o calendário e as regras efetivamente suportados pelo PSP, com risco de chargeback e proteção do consumidor considerados;
- não prometer que o Yvenist retém dinheiro em escrow ou controla livremente a data de liquidação sem autorização contratual e regulatória;
- não criar saldo de carteira do consumidor ou do fornecedor como obrigação financeira própria sem análise especializada.

O painel do fornecedor deve mostrar status do pagamento, saldo estimado, motivo de retenção pelo PSP, previsão de liquidação quando disponível e histórico conciliável.

## 10. Contratação e documentos

O consumidor não terá uma etapa separada de “aceitar orçamento do fornecedor”. Porém, quando pagar e formalizar a contratação, deverá conhecer e aceitar os termos da compra/serviço.

Para cada `SupplierSubOrder` confirmado e contratado, gerar um registro contratual imutável com:
- identificação do consumidor e fornecedor;
- identificação do pedido e subpedido;
- descrição e versão dos itens/pacotes;
- conteúdo incluído, excluído e opcionais;
- data, horário, endereço/área e condições de acesso;
- quantidades e requisitos do evento;
- preço por linha, descontos, taxa, total, plano de pagamento e comissão do fornecedor;
- condições de cancelamento, reembolso, alteração e no-show;
- obrigações de cada parte;
- registros de aceite, data/hora, versão dos termos e evidência de pagamento.

O registro contratual pode ser uma confirmação digital estruturada e PDF/HTML para consulta; não pressupor assinatura eletrônica qualificada sem necessidade. Alterações materiais devem gerar aditivo/versionamento e aceite explícito das partes afetadas. Não editar retroativamente o snapshot original.

Separar:
- termos de uso/serviço do Yvenist;
- contrato ou condições da prestação entre consumidor e fornecedor;
- contrato de participação do fornecedor no marketplace;
- recibo/registro de pagamento e repasse;
- política de privacidade e avisos de dados.

## 11. Políticas operacionais propostas

### 11.1. Prazos de resposta do fornecedor

Configurar `response_deadline` por categoria, urgência e antecedência do evento. Não usar o mesmo prazo para kit pronto, salão, buffet e decoração personalizada.

Ao expirar:
- nenhum silêncio equivale a aceitação;
- o subpedido passa a `expired`;
- consumidor recebe notificação;
- o sistema mostra alternativas;
- o histórico registra prazo, notificações e eventual justificativa.

Definir prazos numéricos com dados de piloto e aprovação dos responsáveis.

### 11.2. Cancelamento pelo consumidor

Estruturar por estado e categoria:
- **Antes do envio:** consumidor edita/exclui itens sem cobrança.
- **Pedido enviado, sem confirmação do fornecedor:** permitir cancelamento simples da solicitação; não cobrar por parte ainda não contratada.
- **Fornecedor confirmou, mas pagamento/contrato não concluiu:** cancelar/liberar a reserva temporária sem tratar como serviço já prestado.
- **Depois da contratação:** aplicar termos específicos da categoria, exibidos antes do checkout, sem afastar direitos legais.
- **Cancelamento parcial:** afetar o subpedido/linha selecionada; não cancelar automaticamente os demais fornecedores independentes.
- **Arrependimento legal:** disponibilizar canal simples pela mesma jornada de contratação, com avaliação jurídica de aplicabilidade e tratamento de reembolso.

Não fixar multa, percentual retido ou janela universal neste documento. Qualquer retenção após cancelamento exige base contratual clara, proporcionalidade, comprovação de custo quando cabível e revisão jurídica.

### 11.3. Cancelamento pelo fornecedor

- fornecedor informa motivo e comunica imediatamente;
- subpedido não executado não gera comissão adquirida;
- iniciar reembolso da parcela correspondente conforme regras e estado do PSP;
- informar o consumidor e oferecer substituição quando viável;
- registrar reincidência e evidências;
- aplicar medidas graduais e revisáveis (orientação, alerta, redução temporária de exposição, suspensão de agenda ou suspensão do cadastro), com processo de contestação e exceção para eventos justificáveis.

Não copiar multa do Airbnb. Qualquer penalidade financeira ao fornecedor requer aprovação conjunta, contrato claro, análise de proporcionalidade e parecer jurídico.

### 11.4. Atraso, no-show e falha de qualidade

Registrar horário contratado, atualizações e evidências de chegada/entrega. Para atraso, informar o consumidor e oferecer opções realistas. Para no-show do fornecedor, abrir ocorrência, proteger o consumidor e avaliar reembolso da parte não prestada. Para no-show do consumidor, aplicar apenas condições previamente contratadas e revisadas juridicamente.

Não decidir disputa automaticamente com base apenas na afirmação de uma das partes.

### 11.5. Alterações, reclamações e disputas

- alteração de preço, escopo, data ou fornecedor exige histórico e consentimento explícito;
- vincular chat, anexos e atendimento ao pedido/subpedido;
- abrir disputa formal separada do atendimento comum;
- indicar prazo, responsável, evidências solicitadas e próximo passo;
- permitir resolução parcial por fornecedor sem apagar o evento inteiro;
- preservar logs de decisão e reembolso;
- tratar chargeback conforme regras do PSP e fornecer evidências do contrato, aceite, comunicação e prestação.

## 12. Dados, transparência e proteção do consumidor

O CDC trata, entre outros temas, de conhecimento prévio do contrato, interpretação favorável ao consumidor, direito de arrependimento em contratações fora do estabelecimento e cláusulas abusivas. O Decreto 7.962/2013 trata de informações claras na contratação eletrônica, atendimento e mecanismos para exercício do direito de arrependimento. A aplicação concreta a serviços agendados, itens personalizados, produtos perecíveis, pacotes e eventos deve ser analisada por advogado brasileiro; não criar uma exceção genérica por conta própria.

Referências:
- https://www.planalto.gov.br/ccivil_03/leis/l8078compilado.htm
- https://www.planalto.gov.br/ccivil_03/_ato2011-2014/2013/decreto/d7962.htm

O fato de os responsáveis desejarem que consumidor e fornecedor vejam suas identidades desde o início não autoriza expor dados desnecessários. Definir quais dados de perfil e contato são exibidos em cada estágio; cumprir finalidade, necessidade, transparência e segurança segundo a LGPD.

Referências:
- https://www2.camara.leg.br/legin/fed/lei/2018/lei-13709-14-agosto-2018-787077-normaatualizada-pl.html
- https://www.gov.br/cti/pt-br/acesso-a-informacao/lei-geral-de-protecao-de-dados

## 13. Decisões que ainda exigem aprovação conjunta

A direção de receita já foi aprovada; os valores e condições abaixo ainda não:

| ID | Decisão | Minha recomendação inicial | Estado |
|---|---|---|---|
| COM-01 | Comissão piloto | 10% sobre base comissionável por subpedido concluído | PENDENTE |
| COM-02 | Base de comissão | Linhas concluídas após desconto financiado pelo fornecedor; demais componentes segregados e revisados | PENDENTE |
| COM-03 | Taxa do PSP | Transparente e separada; decidir se Yvenist absorve ou deduz do repasse | PENDENTE |
| PAY-02 | Pagamento de evento | Após confirmação dos fornecedores; suportar pagamento integral e deixar depósito/saldo habilitado por política aprovada | PENDENTE |
| PAY-03 | Janela de reserva após aceite do fornecedor | Janela temporária por categoria, expirando sem pagamento | PENDENTE |
| OPS-01 | SLA de fornecedor | Configurar por categoria e urgência; determinar números após piloto | PENDENTE |
| OPS-02 | Cancelamento do consumidor | Regra por etapa/categoria, respeitando direitos legais; sem multa padrão | PENDENTE |
| OPS-03 | Cancelamento do fornecedor | Reembolso da parte não prestada, medidas graduais e justificativa/contestação | PENDENTE |
| OPS-04 | Gatilho de conclusão | Confirmação do consumidor ou evidência/timeout de resolução definido por categoria | PENDENTE |
| PAY-04 | Liquidação e repasse | Split pelo PSP e calendário do provedor; sem custódia própria presumida | PENDENTE |
| ADS-01 | Exposição patrocinada | Posições limitadas, identificadas e elegibilidade antes da promoção | PENDENTE |
| SUB-01 | Assinatura de consumidores | Fora do MVP; benefícios e preço serão definidos depois | FUTURO |

## 14. Critérios de aprovação para entrar em produção

Não habilitar transações reais até que:
1. os responsáveis aprovem COM-01 a PAY-04 e OPS-01 a OPS-04;
2. advogado revise contratos, cancelamentos, direito de arrependimento, responsabilidades e identidade do marketplace;
3. contador valide emissão fiscal, base de comissão, tributos, conciliação e repasses;
4. PSP confirme por contrato e documentação a configuração multi-vendedor, split, reembolso parcial, chargeback e agenda de liquidação;
5. fornecedor complete onboarding/KYC aplicável;
6. consumidor veja preço total, condições e termos antes de pagar;
7. testes em sandbox cubram pagamento aprovado/recusado/pendente, webhook duplicado, estorno total/parcial, chargeback e fornecedor desconectado;
8. suporte/backoffice consigam localizar pedido, subpedido, pagamento, contrato, repasse e disputa.

## 15. Fontes e limitações

Fontes consultadas em 2026-11-18. Conteúdo de terceiros é referência de mecanismo, não aconselhamento jurídico, contábil ou autorização para operar serviço de pagamento. Taxas, APIs, elegibilidade e políticas comerciais podem mudar; revalidar diretamente com o PSP antes de escolher fornecedor ou implementar integração.


## 10. Programa de lançamento e comissão progressiva

A proposta comercial específica para COM-01 está detalhada em `COMMISSION_POLICY_AND_FOUNDING_PARTNER_LAUNCH_2026-11-18.md`. O programa busca reduzir a barreira de entrada para fornecedores iniciais sem comprometer a sustentabilidade futura: taxa de fundador de 3%, expansão a 5% e taxa-alvo de 10% em maturidade. A progressão exige métricas, aviso prévio e aceite contratual; não é automática por tempo. A proposta ainda aguarda aprovação conjunta de Keven e Rafael e revisão jurídica/contábil.


## 10. Programa de Parceiros Fundadores e mercado de lançamento

- Primeira área: Campo Grande / Zona Oeste do Rio, com núcleo de aquisição em Campo Grande e cobertura por área efetivamente atendida.
- Meta: 20 fornecedores fundadores ativos e distintos, distribuídos em quatro famílias com cinco fornecedores cada: espaços/salões; buffet/alimentação; decoração/locação; confeitaria/doces/kits.
- Atrações/entretenimento, foto/vídeo, papelaria, som/iluminação e demais categorias podem entrar em ondas posteriores após densidade e suporte.
- A comissão 3% / 5% / 10%, prazo fundador de 12 meses desde a primeira venda concluída, gates e aviso de 60 dias estão aprovados conjuntamente como regra de negócio; ativação financeira continua dependendo de COM-02/COM-03 e revisão especializada.
- Plano operacional e referências: `LOCAL_MARKET_LAUNCH_PLAN_CAMPO_GRANDE_ZONA_OESTE_2026-11-18.md`.

# Casos de Uso

## UC01: Realizar Venda

### Ator(es):
* Cliente
* Funcionário do caixa
* Operadora de pagamentos

### Interessado(s) e interesse(s):
* **Cliente**: Deseja realizar a compra de produtos de forma rápida e eficiente.
* **Funcionário do caixa**: Deseja processar a venda de maneira correta e eficiente.
* **Gerente da mercearia**: Interesse em garantir que as vendas sejam realizadas corretamente e que o fluxo de caixa esteja atualizado.
* **Operadora de pagamentos**: Interesse em autorizar e processar os pagamentos realizados.

### Pré-condições:
* O sistema está em funcionamento.
* O funcionário do caixa está autenticado no sistema.
* O cliente selecionou os produtos que deseja comprar.

### Pós-condições:
* A venda foi registrada no sistema.
* O pagamento foi realizado com sucesso.
* O estoque foi atualizado conforme os produtos vendidos.
* Um comprovante foi gerado e entregue ao cliente.

### Questões em aberto:
* Quais serão as políticas de parcelamento para pagamentos com cartão de crédito?
* Existe alguma integração com programas de fidelidade ou descontos?
* Como será o tratamento para devoluções ou cancelamentos após o pagamento?

### Fluxo Principal:
1. O cliente escolhe os produtos e leva ao caixa.
   
2. **[IN]** O funcionário registra os itens no sistema.

3. **[OUT]** O sistema exibe o valor total da compra.

4. **[IN]** O funcionário finaliza o registro da venda.

5. **[OUT]** O sistema exibe as formas de pagamento disponíveis.

6. **[IN]** O cliente escolhe a forma de pagamento:
   * **6.1. Pagamento com dinheiro**
   * **6.2. Pagamento com cartão de débito**
   * **6.3. Pagamento com cartão de crédito**
   * **6.4. Pagamento com Pix**
   * **6.5. Pagamento com vale refeição**

7. **[OUT]** O sistema confirma o pagamento e gera o comprovante.

8. **[IN]** O funcionário entrega o comprovante ao cliente e, se houver, o troco.

### Variantes

#### 6.1. Pagamento com dinheiro
1. O cliente entrega as notas ao funcionário.
2. O funcionário registra o valor recebido no sistema.
3. O sistema calcula e exibe o valor do troco (se aplicável).
4. O funcionário entrega o troco ao cliente, se houver.

#### 6.2. Pagamento com cartão de débito
1. O cliente insere ou aproxima o cartão na máquina de pagamento.
2. O sistema envia os dados do cartão para a operadora de cartões.
3. A operadora confirma a autorização do pagamento.
4. O sistema registra o pagamento como concluído.

#### 6.3. Pagamento com cartão de crédito
1. O cliente insere ou aproxima o cartão na máquina de pagamento.
2. O sistema exibe as opções de parcelamento, se aplicável.
3. O cliente escolhe a opção de parcelamento (se disponível).
4. O sistema envia os dados do cartão e parcelamento para a operadora de cartões.
5. A operadora confirma a autorização do pagamento.
6. O sistema registra o pagamento como concluído.

#### 6.4. Pagamento com Pix
1. O sistema solicita uma chave Pix à operadora de pagamentos.
2. O sistema exibe a chave Pix ou QR Code para pagamento.
3. O cliente realiza o pagamento via aplicativo bancário.
4. A operadora de pagamentos confirma a transação.
5. O sistema registra o pagamento como concluído.

#### 6.5. Pagamento com vale refeição
1. O cliente insere ou aproxima o cartão de vale refeição na máquina de pagamento.
2. O sistema envia os dados do cartão para a operadora de vale refeição.
3. A operadora confirma a autorização do pagamento.
4. O sistema registra o pagamento como concluído.

### Exceções

#### 6.1. Pagamento com dinheiro insuficiente
1. O sistema alerta que o valor recebido é insuficiente.
2. O cliente entrega um valor adicional ou cancela a compra.

#### 6.2. Pagamento com cartão de débito recusado
1. O sistema informa que o pagamento foi recusado.
2. O cliente tenta outro cartão ou escolhe outra forma de pagamento.

#### 6.3. Pagamento com cartão de crédito recusado
1. O sistema informa que o pagamento foi recusado.
2. O cliente tenta outro cartão ou escolhe outra forma de pagamento.

#### 6.4. Pagamento com Pix não realizado
1. O sistema informa que o pagamento não foi confirmado.
2. O cliente verifica se o pagamento foi concluído corretamente ou escolhe outra forma de pagamento.

#### 6.5. Pagamento com vale refeição recusado
1. O sistema informa que o pagamento foi recusado.
2. O cliente tenta outro cartão ou escolhe outra forma de pagamento.

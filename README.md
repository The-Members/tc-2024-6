# Descrição do Projeto

Desenvolver uma API em Laravel 11 para processar pagamentos de forma assíncrona. A API deve receber os dados do valor do pagamento, a forma de pagamento, o CPF do comprador e o ID do produto. Cada método de pagamento será processado por um provedor diferente, e o processamento deve ser realizado de forma assíncrona para garantir a escalabilidade e a eficiência do sistema.

# Requisitos da API

## Rota:

    [POST] localhost:8000/api/payment

## Input:
- payment_method: Define o método de pagamento. Pode ser 'boleto', 'pix' ou 'credit_card'.
- amount: O valor do pagamento, em formato float.
- buyer_document: O CPF do comprador, em formato string.
- product_id: O ID do produto a ser comprado, em formato string.

## Exemplo de Request:

```json
{
    "amount": 100.50,
    "payment_method": "pix",
    "buyer_document": "12345678901",
    "product_id": "ABC123"
}
```

## Detalhamento das Funcionalidades

### Recebimento de Dados:
A API deve validar os dados recebidos, garantindo que o amount seja um valor positivo, que o payment_method seja um dos valores permitidos ('boleto', 'pix', 'credit_card'), e que o buyer_document esteja no formato correto de CPF.

### Processamento Assíncrono:
O processamento do pagamento deve ser realizado de forma assíncrona, para evitar bloqueios e melhorar a performance do sistema.

### Provedores de Pagamento:

Cada método de pagamento ('boleto', 'pix', 'credit_card') deve ser processado por um provedor diferente.
-    Boleto: Provedor A
-    Pix: Provedor B
-    Cartão de Crédito: Provedor C
  
A escolha do provedor deve ser configurável para facilitar mudanças futuras. Os nomes dos provedores são opcionais, sinta-se livre para nomeá-los.

### Resposta da API:
A resposta inicial da API deve confirmar o recebimento do pedido de pagamento e informar que o processamento está em andamento.
Exemplo de Resposta:
```json
{
    "status": "processing",
    "message": "Payment request received and is being processed."
}
```

## Notificação de Status:
Uma vez que o processamento do pagamento seja concluído, o status (sucesso ou falha) deve ser atualizado e, opcionalmente, o cliente pode ser notificado via e-mail ou outra forma de comunicação.



# Envio

O link do repositor deve ser enviado para os emails: 

    lucas.cardial@themembers.com.br danilo@themembers.com.br david@themembers.com.br

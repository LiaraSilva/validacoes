# PROJETOS COM VALIDAÇÕES

## Validação de CPF

### Recursos ultilizados:

### document.getElementById('cpfForm'):
*  Obtém o valor do campo de entrada de CPF.

### addEventListener('submit', function(event):
*  Impede o envio do formulário.

### event.preventDefault():
* Impede que o formulário seja enviado para o servidor, o que é útil para validar o CPF localmente.

### if :
* Verifica se o CPF é válido chamando a função validarCPF. Dependendo do resultado, exibe uma mensagem apropriada.

### cpf = cpf.replace(/[^\d]+/g, ''):
* Remove todos os caracteres que não são dígitos. O regex '/[^\d]+/g' encontra todos os caracteres que não são números e os substitui por uma string vazia.



## Validação de Email


###

###
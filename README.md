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

### if (cpf.length !== 11 || /^(\d)\1{10}$/.test(cpf)) { return false; }:
* cpf.length !== 11: Verifica se o CPF tem exatamente 11 dígitos.
* /^(\d)\1{10}$/.test(cpf): Verifica se todos os 11 dígitos são iguais (ex.: "11111111111"). Se todos forem iguais, é um CPF inválido.

### for(let i = 1; i <= 9; i++) { ... }: 
* Calcula a soma ponderada dos primeiros 9 dígitos do CPF para validar o primeiro dígito verificador.

### soma += parseInt(cpf.substring(i - 1, i)) * (11 - i);:
* Adiciona o produto do dígito atual pelo seu peso na soma.

### resto = (soma * 10) % 11;:
* Calcula o resto da divisão da soma por 11 e ajusta se necessário.

### if(resto === 10 || resto === 11) { resto = 0; }:
* Ajusta o resto para 0 se for 10 ou 11.

### if(resto !== parseInt(cpf.substring(9, 10))) { return false; }:
* Compara o resto com o primeiro dígito verificador no CPF.

### for(let i = 1; i <= 10; i++) { ... }:
* Calcula a soma ponderada dos primeiros 10 dígitos para validar o segundo dígito verificador.

### soma += parseInt(cpf.substring(i - 1, i)) * (12 - i);:
* Adiciona o produto do dígito atual pelo seu peso na soma.

### resto = (soma * 10) % 11;:
* Calcula o resto da divisão da soma por 11 e ajusta se necessário.

### if(resto === 10 || resto === 11) { resto = 0; }:
* Ajusta o resto para 0 se for 10 ou 11.

### if(resto !== parseInt(cpf.substring(10, 11))) { return false; }:
* Compara o resto com o segundo dígito verificador no CPF.

### return true;:
* Se ambos os dígitos verificadores estiverem corretos, o CPF é considerado válido.

## Validação de Email

### Recursos Ultilizados:

### document.forms[0].email.value == "":
* Verifica se o campo de e-mail está vazio.

### document.forms[0].email.value.indexOf('@') == -1:
* Verifica se o caractere '@' está presente no e-mail. Se não estiver, indexOf retorna -1.

### document.forms[0].email.value.indexOf('.') == -1:
* Verifica se o caractere '.' está presente no e-mail. Se não estiver, indexOf retorna -1.

### alert("Email informado");:
* Exibe uma mensagem de sucesso.

### document.getElementById('email').innerHTML = document.forms[0].email.value;:
* Esta linha tenta atualizar o conteúdo HTML do elemento com o ID 'email'. No entanto, o ID 'email' provavelmente está associado ao campo de entrada, e não a um elemento que possa exibir texto. Isso pode não funcionar como esperado.

### document.forms[0].email.value:
* Obtém o valor do campo de e-mail. Para garantir que você está acessando o formulário correto, considere usar um ID para o formulário em vez de document.forms[0].

### email.includes('@') e email.includes('.'):
* Verificam a presença dos caracteres '@' e '.' usando métodos mais modernos.

### Expressão Regular emailRegex:
* Valida o formato básico do e-mail.

### document.getElementById('emailDisplay').textContent = email;:
* Atualiza o conteúdo de um parágrafo com ID 'emailDisplay' para mostrar o e-mail informado.
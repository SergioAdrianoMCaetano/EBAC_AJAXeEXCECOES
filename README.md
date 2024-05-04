#EBAC_AJAX e EXEÇÕES

Este é um código HTML que cria uma interface de usuário para um formulário de pedido. Ele usa a biblioteca Bootstrap para estilização e a biblioteca jQuery para manipulação de eventos e AJAX. Aqui está uma explicação detalhada:

1. `$(document).ready(function(){...});`: Este é um evento jQuery que é acionado quando o documento HTML termina de carregar. Todo o código dentro desta função será executado assim que a página estiver pronta.

2. `$('#cep').mask('00000-000');`: Esta linha está aplicando uma máscara de entrada ao elemento com o id 'cep'. A máscara '00000-000' é usada para formatar a entrada como um CEP brasileiro.

3. `$('#btn-buscar-cep').click(function(){...});`: Este é um manipulador de eventos que é acionado quando o botão com o id 'btn-buscar-cep' é clicado. O código dentro desta função será executado quando o botão for clicado.

4. Dentro do manipulador de clique, o código faz uma requisição AJAX para a API ViaCEP para buscar informações sobre o CEP fornecido. Se a requisição for bem-sucedida (`.done(function(resposta){...})`), ele preenche o campo de endereço com as informações retornadas. Se a requisição falhar (`.fail(function(){...})`), ele exibe um alerta para o usuário.

5. O bloco `try-finally` é usado para garantir que, independentemente do resultado da requisição AJAX, o ícone de carregamento será escondido e o texto do botão será mostrado novamente após 2 segundos.

6. `$('#formulario-pedido').submit(function(evento){...});`: Este é um manipulador de eventos que é acionado quando o formulário com o id 'formulario-pedido' é enviado. Ele impede a ação padrão de envio do formulário (com `evento.preventDefault();`) e verifica se o campo de nome está vazio. Se estiver vazio, ele lança um erro.

O código comentado (`// fetch(endpoint)...`) é uma alternativa ao uso de `$.ajax()`, usando a API Fetch nativa do JavaScript para fazer a requisição HTTP. Ele está comentado, então não está sendo usado neste momento
Tabela Fipe API
------------------------------------------------------------------------------

Este projeto em Java é uma aplicação de console que realiza consultas à Tabela Fipe, permitindo buscar informações de preços de veículos (carros, motos e caminhões) com base na marca, modelo e ano. Utilizando a API pública da Tabela Fipe, a aplicação obtém os dados e os exibe em um formato organizado.

------
Estrutura do Projeto e principais Componentes: 

IConverteDados: (Interface) define métodos para converter dados JSON em objetos Java:


obterDados: Converte uma string JSON em um objeto do tipo especificado.


obterLista: Converte uma string JSON em uma lista de objetos do tipo especificado.


ConverteDados: Implementa a interface IConverteDados usando a biblioteca Jackson (ObjectMapper) para converter o JSON recebido da API em objetos Java.


ConsumoApi: Realiza requisições HTTP para a API da Tabela Fipe, obtendo os dados JSON para serem processados:


obterDados: Recebe uma URL, realiza a requisição e retorna a resposta em formato JSON.


Principal: Controla o fluxo principal da aplicação, exibindo o menu e capturando as entradas do usuário para realizar consultas de:

Marcas (Carros, Motos, Caminhões);

Modelos de uma marca específica;

Ano de fabricação e valores de mercado para modelos específicos.

-----------------------------------------------------------------
TabelaFipeApplication: Classe principal da aplicação que inicializa o Spring Boot e executa o método run, chamando a classe Principal para iniciar o menu de consulta.



Classes de Modelos:

Veiculo: Usa anotações do Jackson (@JsonAlias e @JsonIgnoreProperties) para mapear os campos JSON em propriedades Java. Representa os detalhes do veículo, como valor, marca, modelo, ano e tipo de combustível.

Dados: Representa dados básicos de resposta JSON com um código e nome. Usado para listar marcas e modelos.
 

Modelos: Encapsula uma lista de objetos Dados, representando uma coleção de modelos de veículos.

Funcionalidades da Aplicação
Seleção de Tipo de Veículo: O usuário pode escolher entre Carro, Moto e Caminhão.

Listagem de Marcas: Após a escolha do tipo de veículo, a aplicação lista todas as marcas disponíveis.

Busca de Modelos: O usuário seleciona uma marca, e a aplicação lista os modelos dessa marca.

Busca por Ano e Valor de Veículo: Para um modelo específico, a aplicação exibe os valores de mercado dos últimos 5 anos.

-----------------------------------------------------------------


Exemplo de Uso:
ao iniciar, o usuário escolhe o tipo de veículo.

A aplicação lista as marcas desse tipo.

Após escolher uma marca, o usuário seleciona o modelo.

A aplicação então exibe os valores dos últimos 5 anos para o modelo selecionado.

-----------------------------------

Tecnologias e Bibliotecas Utilizadas:

Java 17

Spring Boot (para inicializar a aplicação)

Jackson (para conversão de JSON)

HTTP Client (para chamadas à API da Tabela Fipe)

-------------------------------------

Instalação e Execução para executar a aplicação:

Clone o repositório e entre na pasta do projeto.

Compile o projeto e execute o comando:

mvn spring-boot:run

A aplicação iniciará no terminal com um menu para navegação.

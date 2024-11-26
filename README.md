# Aula 25-11 - App Conversão de moeda

## Avaliação

* Implemente para que o usuário possa fazer conversão de outras moedas (mínimo + 3 moedas);
* Descreva abaixo o seu entendimento acerca desta atividade, explorando as funcionalidades das classes que contruímos e os principais pontos da aplicação;

## Entrega

* Clone este repositório e faça o que se pede;
* Realize um commit das suas alterações no seu repositório;
* Envie o link do repositório na avaliação gerada no classroom;

# Descritivo do Aluno:

## Conversor de Moedas Angular

Implementação de um conversor de moedas utilizando Angular com JavaScript, com a API AwesomeAPI para obter as taxas de câmbio atualizadas.

### ConversorService

O `ConversorService` é um serviço no Angular que facilita a conversão de moedas. Ele se comunica com a API AwesomeAPI para obter as taxas de câmbio atuais de diversas moedas por meio de requisições HTTP, retornando os dados necessários para a aplicação.

#### Como Funciona

##### Decorador @Injectable

O decorador `@Injectable` marca a classe `ConversorService` como um serviço que pode ser injetado em outros componentes. Isso garante que a instância do serviço seja compartilhada entre todos os componentes da aplicação.

##### Método converterMoeda

O método `converterMoeda(moeda: String)` recebe um código de moeda, como `BRL-USD`, e realiza a conversão entre as moedas especificadas. Ele faz uma requisição HTTP utilizando a biblioteca `Axios` para acessar a API e retorna a taxa de câmbio correspondente.

### Axios

O Axios é uma biblioteca de requisições HTTP que facilita a comunicação com APIs utilizando Promises. Com o Axios, pode-se realizar solicitações GET para obter as taxas de câmbio de forma simples e eficiente. A função `axios.get()` é utilizada para realizar a requisição dos dados necessários.

### ConverterMoedaComponent

O `ConverterMoedaComponent` é um componente Angular que utiliza o `ConversorService` para converter valores monetários entre diferentes moedas. Ele permite que o usuário escolha a moeda de origem e destino, insira um valor e calcule a conversão com base nas taxas de câmbio atuais.

#### Como Funciona

##### Estrutura do Componente

O `ConverterMoedaComponent` possui três propriedades principais e um método:

- `opcaoEscolhida`: A moeda escolhida pelo usuário para conversão (exemplo: `BRL-EUR`).
- `valor`: O valor inserido pelo usuário para conversão.
- `resultado`: O valor resultante da conversão, calculado com base na taxa de câmbio.

##### Método calcularConversao

O método `calcularConversao` é chamado quando o usuário deseja realizar a conversão de moeda. Ele segue os seguintes passos:

1. Chama o método `converterMoeda()` do serviço `ConversorService`, passando a moeda escolhida pelo usuário.
2. A API retorna os dados da conversão, que são processados para extrair a taxa de câmbio (`high`).
3. Multiplica o valor inserido pelo usuário pela taxa de câmbio, calculando o valor convertido.
4. O resultado é exibido no componente.


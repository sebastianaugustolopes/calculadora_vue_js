# Calculadora Aritmética

Este projeto é uma calculadora aritmética simples desenvolvida com Vue.js. A calculadora permite realizar operações básicas como soma, subtração, multiplicação e divisão.

## Funcionalidades

- Inserir dois números
- Selecionar a operação desejada (soma, subtração, multiplicação, divisão)
- Exibir o resultado do cálculo

## Estrutura do Projeto

O projeto está estruturado da seguinte forma:

```
calculadora_vue/
├── vue-project/
│   ├── src/
│   │   ├── components/
│   │   │   └── Form.vue
│   │   └── App.vue
│   ├── public/
│   └── package.json
└── README.md
```

## Instalação

1. Clone o repositório:
   ```bash
   git clone <URL_DO_REPOSITORIO>
   ```
2. Navegue até o diretório do projeto:
   ```bash
   cd calculadora_vue/vue-project
   ```
3. Instale as dependências:
   ```bash
   npm install
   ```

## Uso

1. Inicie o servidor de desenvolvimento:
   ```bash
   npm run dev
   ```
2. Abra o navegador e acesse `http://localhost:3000` para ver a calculadora em ação.

## Componentes

### Form.vue

Este componente é responsável por renderizar o formulário da calculadora, onde o usuário pode inserir os números e selecionar a operação.

### App.vue

Este componente é o componente principal da aplicação, que gerencia o estado e a lógica da calculadora.

## Estilo

Os estilos são definidos no próprio componente utilizando `<style scoped>`, garantindo que os estilos sejam aplicados apenas ao componente correspondente.

## Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir uma issue ou enviar um pull request.

## Licença

Este projeto está licenciado sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

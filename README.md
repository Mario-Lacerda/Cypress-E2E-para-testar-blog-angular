# Desafio Dio - Utilizando o Cypress E2E para testar um Blog em Angular



O Cypress é uma ferramenta de teste de ponta a ponta (E2E) para aplicativos da web. Ele permite que você escreva testes que simulam o comportamento do usuário real, como clicar em botões, inserir texto e verificar o resultado.

Neste projeto, criaremos um conjunto abrangente de testes E2E para um Blog em Angular usando o Cypress. Esses testes cobrirão diferentes funcionalidades do blog, como criar, editar e excluir posts.



### **Pré-requisitos**

- Node.js e npm instalados
- Angular CLI instalado



### **Passos**



### **1. Configurar o Projeto Angular**

- Crie um novo projeto Angular usando `ng new my-blog`.
- Navegue até o diretório do projeto e instale o Cypress usando `npm install cypress --save-dev`.



### **2. Configurar o Cypress**

- Execute `cypress open` para criar um novo projeto do Cypress.
- Selecione o projeto Angular como o aplicativo a ser testado.



### **3. Escrever Testes**

Crie arquivos de teste separados para cada funcionalidade que deseja testar, como `cypress/integration/posts.spec.js` para testes relacionados a posts.



### **Testes de Criação de Posts**

javascript



```javascript
describe('Create Post', () => {
  it('should create a new post', () => {
    cy.visit('/');
    cy.get('a[href="/posts/new"]').click();
    cy.get('input[name="title"]').type('My New Post');
    cy.get('textarea[name="body"]').type('This is the body of my new post.');
    cy.get('button[type="submit"]').click();

    cy.contains('h1', 'My New Post');
  });
});
```



### **Testes de Edição de Posts**

javascript



```javascript
describe('Edit Post', () => {
  it('should edit an existing post', () => {
    cy.visit('/posts/1');
    cy.get('a[href="/posts/1/edit"]').click();
    cy.get('input[name="title"]').clear().type('Edited Post Title');
    cy.get('button[type="submit"]').click();

    cy.contains('h1', 'Edited Post Title');
  });
});
```



### **Testes de Exclusão de Posts**

javascript



```javascript
describe('Delete Post', () => {
  it('should delete an existing post', () => {
    cy.visit('/posts/1');
    cy.get('a[href="/posts/1/delete"]').click();

    cy.contains('h1', 'Posts').should('exist');
  });
});
```



### **4. Executar e Depurar Testes**



- Execute todos os testes usando `cypress run`.
- Use a interface do usuário do Cypress para depurar testes com falha e identificar problemas.



### **5. Melhorar e Manter Testes**



- Refatore e melhore os testes ao longo do tempo para garantir que eles sejam confiáveis e fáceis de manter.
- Adicione novos testes para cobrir novas funcionalidades ou corrigir bugs.



### **Conclusão**



Ao concluir este projeto, você terá criado um conjunto abrangente de testes E2E para um Blog em Angular usando o Cypress. Esses testes ajudarão a garantir a qualidade e a estabilidade do seu aplicativo. Você também terá adquirido experiência valiosa no uso do Cypress para testar aplicativos Angular.

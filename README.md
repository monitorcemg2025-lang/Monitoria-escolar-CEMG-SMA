# SEDUC - Monitoria Busca Ativa e Desempenho Escolar

Sistema web para registro de horários de monitores, faltas de alunos, lista de alunos e geração de relatórios em PDF.

## Como Executar

1. **Pré-requisitos**:
   - Node.js instalado (para testes locais, opcional).
   - Conta no Render.com para deploy.

2. **Deploy no Render.com**:
   - Crie um novo "Web Service" no Render.
   - Conecte ao repositório Git contendo este projeto.
   - Configure:
     - **Build Command**: `npm install` (se usar dependências locais, caso contrário, não necessário).
     - **Start Command**: Não necessário (servir arquivos estáticos).
     - **Environment**: Static Site.
   - Faça commits pequenos para builds rápidos (1-5 minutos).
   - Use "Clear build cache and redeploy" no painel do Render em caso de erros de build.

3. **Estrutura do Projeto**:
   - `index.html`: Página de login com brasão.
   - `main.html`: Registro de horários do monitor.
   - `absences.html`: Registro de faltas dos alunos.
   - `students.html`: Lista de 101 alunos reais com botão Copiar.
   - `reports.html`: Geração de relatórios em PDF com brasão.
   - `css/styles.css`: Estilização otimizada.
   - `js/*.js`: Lógica de autenticação, horários, faltas, alunos e relatórios.
   - `img/brasao.png`: Brasão do Centro de Excelência Miguel das Graças (a ser adicionado).
   - `data/mock-api.json`: Simulação de API para autenticação.

4. **Adicionar o Brasão**:
   - Crie a pasta `img/` no diretório `seduc-monitoria/`.
   - Salve o arquivo `brasao.png` (obtido a partir da foto do brasão da escola) em `img/`.
   - Para os PDFs em `reports.js`, converta `brasao.png` para base64 (usando [base64encode.org](https://www.base64encode.org/)) e substitua o valor de `imgData` no código pela string gerada.

5. **Otimizações**:
   - Uso de `document.createDocumentFragment` para renderização rápida.
   - `table-layout: fixed` e `word-wrap: break-word` para tabelas responsivas.
   - Limite de 1000 entradas em `localStorage`.
   - Scripts com `defer` e `async` para evitar bloqueios.
   - Projeto leve (~12 KB).

6. **Notas**:
   - A lista de alunos em `students.js` contém 101 nomes reais (45 no 1º Ano, 35 no 2º Ano, 21 no 3º Ano).
   - Testado para builds rápidos no Render.com.

## Suporte
- Para dúvidas, contate Luiz Felipe.
- &copy; 2025 Luiz Felipe. Todos os direitos reservados.

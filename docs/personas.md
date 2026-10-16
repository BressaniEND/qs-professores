# Personas do Sistema de Alocação de Recursos Acadêmicos

Este documento descreve as personas principais que irão interagir com o sistema de alocação de salas, professores e materiais. Essas personas foram definidas com base no contexto do projeto focado em evitar conflitos de horário e apresentar evidências objetivas de qualidade, segurança, rastreabilidade e desempenho.

---

## 1. Solicitante

**Nome:** Dr. Rafael Mendes  
**Papel:** Docente de Engenharia de Software que solicita recursos para suas aulas  
**Bio:** Professor titular com carga de 4 disciplinas por semestre. Utiliza o sistema para verificar sua grade, solicitar recursos específicos e receber comunicações sobre alterações. Interessado em confirmar disponibilidade de salas e equipamentos antes de planejar suas aulas.

### Objetivos
- Visualizar claramente sua grade de aulas com salas e horários  
- Solicitar recursos especializados (laboratórios, equipamentos específicos) com antecedência  
- Receber notificações pontuais sobre qualquer mudança em seu horário  
- Confirmar presença ou justificar ausências através do sistema  

### Frustrações Atuais
- Recebe alterações de horário por e-mail perdido na caixa de entrada  
- Dificuldade para agendar uso de equipamentos específicos com antecedência  
- Falta de confirmação imediata quando solicita recursos  
- Nenhum canal para reportar problemas na sala após a aula  

### Necessidades do Sistema
- Visualização personalizada da grade com cores por tipo de atividade  
- Formulário simples para solicitação de recursos com approval workflow  
- Notificações por push e e-mail para alterações críticas  
- Histórico de solicitações e seu status (pendente, aprovada, negada)  
- Mobile-first design para acesso rápido entre aulas  
- Feedback imediato ao confirmar presença ou reportar incidente  

### Cenários de Uso-Chave
1. **Início de semestre:** Rafael acessa o sistema para ver sua grade aprovada e solicita uso do laboratório de robótica para suas aulas práticas.
2. **Durante o semestre:** Recebe notificação às 18h de que sua sala foi alterada devido a manutenção emergencial e confirma o recebimento.
3. **Após a aula:** Reporta que o projetor da sala 303 está defeituoso através do sistema, acionando automaticamente a equipe de manutenção.

---

## 2. Responsável

**Nome:** Carla Souza  
**Papel:** Coordinadora Acadêmica responsável pela validação de alocações e acompanhamento de retiradas/devoluções  
**Bio:** Coordinadora com 8 anos de experiência em instituições de ensino superior. Responsável por alocar salas, professores e materiais para mais de 150 disciplinas por semestre, garantindo conformidade com as políticas institucionais e evitando sobreposições de horários. Também supervisiona o uso de materiais e equipamentos pelos professores.

### Objetivos
- Criar horários livres de conflitos de sala, professor e materiais  
- Garantir que todas as disciplinas tenham recursos adequados asignados  
- Aprovar e validar solicitações especiais de recursos  
- Acompanhar retiradas e devoluções de materiais e equipamentos  
- Produzir relatórios de ocupação e utilização de recursos para a administração  
- Adapatar rapidamente o horário diante de imprevistos (substituições, mudanças de sala)  

### Frustrações Atuais
- Processo manual em planilhas leva dias para ser concluído  
- Difficulty em visualizar todos os conflitos simultaneamente  
- Falta de histórico de alterações para auditoria  
- Notificações não automatizadas para professores sobre mudanças  

### Necessidades do Sistema
- Validação em tempo real de conflitos durante a alocação  
- Interface de arrastar e soltar para ajustes rápidos  
- Histórico completo de todas as alterações com usuário, timestamp e motivo  
- Workflow de approval para solicitações especiais  
- Integração com calendários pessoais dos professores (via iCal/Google)  
- Relatórios personalizáveis de taxa de utilização de salas e recursos  
- Controle de acesso baseado em papéis (solicitante vs. responsável vs. administrador)  

### Cenários de Uso-Chave
1. **Planejamento semestral:** Carla importa disciplinas do sistema acadêmico, atribui professores e aloca salas/materiais verificando conflitos em tempo real.
2. **Ajuste emergencial:** Quando um professor se afasta, Carla realoca suas aulas em minutos, recebendo alertas apenas se houver risco de novo conflito.
3. **Acompanhamento de materiais:** Carla valida solicitações de materiais, registra retiradas no momento da aula, e garante devolução posterior.
4. **Prestação de contas:** No final do semestre, Carla gera relatório de utilização de laboratórios para justificar orçamento do próximo ano.

---

## 3. Administrador

**Nome:** Diego Costa  
**Papel:** Administrador técnico que gerencia a plataforma e recursos de manutenção  
**Bio:** Assistente com 3 anos de experiência em secretaria acadêmica. Responsável por cadastrar novas disciplinas, atualizar cadastros de salas e gerar relatórios periódicos de ocupação. Também gerencia bloqueios de manutenção, períodos de manutenção e cadastros de usuários.

### Objetivos
- Reduzir tempo gasto em tarefas operacionais repetitivas  
- Garantir consistência e precisão nos dados inseridos no sistema  
- Fornecer suporte rápido aos usuários que enfrentam dificuldades  
- Produzir relatórios padronizados sob demanda  
- Gerenciar períodos de manutenção e bloqueios de recursos  
- Manter a plataforma funcionando sem erros de cadastro/dupla reserva  

### Frustrações Atuais
- Dados inseridos manualmente em múltiplas plataformas causam inconsistências  
- Relatórios exigem exportação e manipulação em planilhas externas  
- Falta de trilha de auditoria para rastrear quem alterou o que e quando  
- Processo de aprovação de alterações é informal e não documentado  

### Necessidades do Sistema
- Formulários com validação em tempo real (ex: horário não pode ser antes das 7h ou depois das 23h)  
- Workflow de aprovação para alterações no horário já publicado  
- Log completo de todas as ações com usuário, timestamp e diff das alterações  
- Templates de relatório pré-configurados (ocupação por prédio, por dia da semana, etc.)  
- Base de conhecimento integrada para solução de problemas comuns  
- Funcionalidade de desfazer/refazer alterações com confirmação  
- Painel de manutenção para agendar e comunicar períodos de bloqueio  
- Controle de acesso baseado em papéis para diferentes níveis de permissão  

### Cenários de Uso-Chave
1. **Cadastro de nova disciplina:** Diego insere detalhes da nova disciplina de IA, o sistema valida código único, carga horária compatível e sugere professores disponíveis.
2. **Ajuste de horário publicado:** Professor solicita mudança de sala; Diego submete ao workflow de aprovação, que notifica o responsável e registra a decisão.
3. **Agendamento de manutenção:** Diego agenda manutenção no laboratório de robótica, bloqueia o recurso para período específico, e notifica todos os solicitantes.
4. **Relatório de utilização:** Diego gera em segundos relatório mostrando que salas do prédio A têm 65% de ocupação às segundas-feiras às 10h, subsidindo decisão de realocação de aulas.

---

## Mapeamento de Perfis

Os perfis acima correspondem aos papéis definidos no escopo do projeto:

- **Solicitante** ↔ Professor/coordenador que consulta a disponibilidade e cria, altera ou cancela suas reservas
- **Responsável** ↔ Aprova solicitações especiais, valida a alocação de docentes e acompanha retiradas e devoluções de material
- **Administrador** ↔ Gerencia salas, professores, materiais, usuários, bloqueios e períodos de manutenção

---

## Considerações sobre Qualidade nas Personas

Cada persona acima tem necessidades implícitas relacionadas aos pilares de qualidade do projeto:

- **Qualidade:** Todas as personas se beneficiam de validação em tempo real, workflows de approval e histórico detalhado (evitando retrabalho e erros).
- **Segurança:** Controle de acesso baseado em papéis, logs de auditoria e confirmações digitais protegem dados sensíveis e evitam alterações não autorizadas.
- **Rastreabilidade:** Histórico completo de alterações, workflows de approval e assinaturas digitais permitem rastrear toda a decisão desde a origem.
- **Desempenho:** Interface responsiva, relatórios pré-agregados e notificações assíncronas garantem experiência fluida mesmo com volumes altos de dados.

Essas personas servirão como base para a elaboração de user stories, definição de critérios de aceitação e criação de testes que validem não apenas funcionalidades, mas também os atributos de qualidade exigidos pelo projeto.

---

## Estratégia de Qualidade — Documentação de Requisitos

A estratégia de qualidade define as práticas obrigatórias para garantir confiabilidade, segurança e desempenho no sistema de alocação de recursos acadêmicos.

### Testes Automatizados
- **Unitários:** JUnit 5, com testes parametrizados para cobertura de casos de borda.
- **Integração:** Testes de integração com foco em camadas de serviço e repositório.
- **API em Caixa-Preta:** Validação de contratos e comportamento observável das APIs públicas.
- **End-to-End (E2E):** Testes de fluxo completo de usuário (ex: reserva → aprovação → uso → conclusão).

### Ambiente Realista
- **Banco de Dados Containerizado:** Utilização de Testcontainers para prover instâncias reais de banco (PostgreSQL/MySQL) nos testes de integração.
- **Simulação de Integrações Externas:** WireMock para mockar serviços externos (ex: gateways de pagamento, APIs de calendário) em testes de integração e E2E.

### Concorrência
- **Teste de Proteção contra Dupla Reserva:** Teste automatizado que simula requisições simultâneas para o mesmo recurso e verifica que apenas uma é aceita (uso de `ExecutorService` ou ferramentas como Gatling/JMeter em teste de carga leve).

### TDD ou BDD
- **Evidência de Técnica:** Pelo menos uma funcionalidade nova deve ser desenvolvida usando TDD (Red-Green-Refactor) ou BDD (cenários Gherkin com Cucumber ou similar), com commits e logs demonstrando o ciclo.

### Integração Contínua e Análise Estática
- **GitHub Actions:** Workflows configurados para executar em pull requests (build, testes, análise estática).
- **Cobertura de Código:** JaCoCo integrado para gerar relatórios de cobertura (meta: ≥80% em unitários).
- **SonarCloud:** Projeto vinculado ao SonarCloud para análise de qualidade, segurança, duplicidade e dívida técnica.

### Requisitos Não-Funcionais
- **Performance:** Testes de carga com JMeter para validar latência e throughput sob uso simultâneo.
- **Autorização:** Testes específicos de controle de acesso baseado em papéis (RBAC) e elevação de privilégio.
- **Validação de Entrada:** Sanitização e validação rigorosa de todos os inputs (ex: uso de Bean Validation, testes de injeção).
- **Tratamento Seguro de Erros:** Logs estruturados, mensagens de erro genéricas para o usuário (sem vazamento de stack traces) e tratamento centralizado de exceções.

### Uso de Mocks
- **Permitido:** Em testes unitários isolados (ex: mock de dependências de serviço).
- **Obrigatório com Ambiente Real:** Para camadas de persistência (repositórios) e integrações críticas (APIs externas, filas, serviços de terceiros), utilização de Testcontainers ou WireMock para validar comportamento real.

---

## Regras Críticas do Sistema

As regras abaixo são fundamentais para garantir a consistência, segurança e rastreabilidade do sistema de alocação. Devem ser consideradas na implementação e nos testes.

### Regras de Tempo e Concorrência

1. **Tempo de início e término:** O horário de término deve ser posterior ao horário de início de qualquer reserva.
2. **Sem sobreposição:** Reservas do mesmo recurso (sala, material ou professor) não podem se sobrepor em horário.
3. **Concorrência:** Duas solicitações simultâneas para o mesmo recurso devem produzir uma única reserva aceita (evitar dupla reserva).
4. **Manutenção:** Recursos em período de manutenção não podem ser reservados.

### Estados e Auditoria

O ciclo de vida de uma reserva segue os estados abaixo:

```
SOLICITADA → APROVADA → EM_USO → CONCLUÍDA
```

**Estados alternativos:**
- **Rejeitada:** Solicitação não atendeu aos critérios de validação.
- **Cancelada:** Reserva foi cancelada antes de ser iniciada.
- **Não compareceu:** Professor não compareceu ao horário agendado.

**Regras de transição:**
- Somente **responsáveis** podem aprovar recursos restritos.
- Reservas iniciadas **não podem ser apagadas** (apenas canceladas ou marcadas como não comparecidas).
- Toda mudança de estado deve gerar um registro de auditoria (quem, quando, estado anterior, estado novo, motivo).

### Regras de Acesso

- **Solicitante:** Cria, altera e cancela suas próprias reservas; consulta disponibilidade.
- **Responsável:** Aprova solicitações especiais, valida alocações de docentes, acompanha retiradas e devoluções.
- **Administrador:** Gerencia cadastros (salas, professores, materiais, usuários), bloqueios e períodos de manutenção.
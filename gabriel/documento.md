# ideia nova projeto

meu projeto é voltado para seguradoras solicitar guinchos e chaveiro para seu clientes

O projeto tem como objetivo oferecer uma plataforma digital voltada ao suporte operacional das seguradoras, permitindo o gerenciamento e acionamento rápido de prestadores de serviços terceirizados. Através do sistema, as seguradoras poderão localizar e contratar serviços como guincho, e outros tipos de assistência de forma ágil, simples e eficiente.

A plataforma reunirá uma base de prestadores cadastrados, com dados como localização, disponibilidade, tipo de veículo e área de cobertura, possibilitando que as seguradoras encontrem o parceiro ideal para cada ocorrência. O sistema também permitirá o registro, acompanhamento e histórico dos atendimentos, promovendo maior controle e organização no processo.

Em uma segunda fase, a plataforma será disponibilizada também em versão de aplicativo, contendo mais funcionalidade como socorro mecânico e chaveiro, facilitando o uso em campo por equipes da seguradora ou prestadores autorizados.

observação: futuramente usuários poderão usar esse sistema sem estar em um seguro.

# casos de usos

### Caso de Uso 1: Solicitar Guincho

- **Ator Principal:** Seguradora
- **Descrição:** Permite que a seguradora registre um pedido de guincho para atender um cliente.
- **Pré-condições:** A seguradora está logada no sistema.
- **Fluxo Principal:**
    1. Seguradora acessa o sistema.
    2. Inicia uma nova solicitação.
    3. Informa a localização e tipo de problema.
    4. Solicitação é registrada no sistema.
- **Pós-condições:** Solicitação registrada e aguardando seleção de prestador.

---

### Caso de Uso 2: Localizar Prestadores

- **Relacionamento:** INCLUDE no "Solicitar Guincho"
- **Ator Principal:** Sistema
- **Descrição:** O sistema busca automaticamente os prestadores de guincho disponíveis com base na localização do cliente.
- **Pré-condições:** Localização válida recebida.
- **Fluxo Principal:**
    1. Sistema utiliza API ou base interna para buscar guinchos próximos.
    2. Lista os disponíveis em tempo real.
- **Pós-condições:** Lista pronta para a seguradora selecionar.

---

### Caso de Uso 3: Selecionar Prestador

- **Relacionamento:** INCLUDE no "Solicitar Guincho"
- **Ator Principal:** Seguradora
- **Descrição:** Permite escolher um prestador da lista sugerida.
- **Pré-condições:** Lista de prestadores gerada.
- **Fluxo Principal:**
    1. Seguradora analisa tempo estimado, avaliações e distância.
    2. Clica em "Selecionar".
- **Pós-condições:** Prestador recebe o chamado.

---

### Caso de Uso 4: Enviar Solicitação

- **Relacionamento:** INCLUDE no "Solicitar Guincho"
- **Ator Principal:** Sistema
- **Descrição:** Envia a ordem de serviço para o guincho selecionado.
- **Pré-condições:** Prestador escolhido.
- **Fluxo Principal:**
    1. Sistema envia notificação para o prestador.
    2. Aguarda resposta.
- **Pós-condições:** Solicitação pendente ou confirmada.

---

### Caso de Uso 5: Atualizar Status

- **Relacionamento:** EXTEND no "Enviar Solicitação"
- **Ator Principal:** Prestador
- **Descrição:** Prestador atualiza o andamento do atendimento.
- **Condição de Extensão:** O prestador aceita o chamado.
- **Fluxo Principal:**
    1. Prestador marca status como "em rota", "no local", "finalizado".
    2. Sistema atualiza para seguradora.
- **Pós-condições:** Status visível no sistema.

---

### Caso de Uso 6: Acompanhar Atendimento

- **Relacionamento:** EXTEND no "Solicitar Guincho"
- **Ator Principal:** Seguradora
- **Descrição:** Permite acompanhar em tempo real o deslocamento do guincho.
- **Condição de Extensão:** Atendimento iniciado.
- **Fluxo Principal:**
    1. Sistema exibe localização atual e tempo estimado.
- **Pós-condições:** Atendimento monitorado até finalização.

---

### Caso de Uso 7: Finalizar Atendimento

- **Relacionamento:** INCLUDE no "Solicitar Guincho"
- **Ator Principal:** Sistema
- **Descrição:** Marca o pedido como finalizado e registra no histórico.
- **Pré-condições:** Prestador marcou como finalizado.
- **Fluxo Principal:**
    1. Sistema registra hora de conclusão e feedback.
- **Pós-condições:** Atendimento arquivado.

---

### Caso de Uso: **Autorizar Cadastro**

- **Ator Principal:** Administrador
- **Descrição:** Permite que um usuário com permissões administrativas aprove ou recuse solicitações de cadastro feitas por seguradoras ou empresas de guincho.
- **Pré-condições:** O cadastro já foi solicitado por um novo usuário (empresa).
- **Fluxo Principal:**
    1. Administrador acessa o painel de solicitações pendentes.
    2. Visualiza os dados da empresa solicitante (nome, CNPJ, documentação, etc.).
    3. Clica em "Aprovar" ou "Recusar".
    4. O sistema registra a decisão e envia notificação ao solicitante.
- **Pós-condições:** O cadastro é ativado (ou recusado) e o acesso ao sistema é liberado apenas após a aprovação.
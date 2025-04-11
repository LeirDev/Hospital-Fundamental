# 🏥 Hospital Fundamental

## Uma história para começar

Um hospital local precisa desenvolver um sistema para gerenciar seus dados clínicos e substituir planilhas e arquivos antigos por um banco de dados funcional.

O objetivo é criar uma estrutura que registre médicos, pacientes, consultas, convênios, receitas médicas e muito mais...

---

## Parte 1 - Mãos à Obra

Analise a seguinte descrição e extraia dela os requisitos para o banco de dados em um diagrama, fluxograma ou afins:

 O hospital necessita de um sistema para sua área clínica que ajude a controlar consultas realizadas. Os médicos podem ser generalistas, especialistas ou residentes e têm seus dados pessoais cadastrados em planilhas digitais. Cada médico pode ter uma ou mais especialidades, que podem ser pediatria, clínica geral, gastroenterologia e dermatologia. Alguns registros antigos ainda estão em formulário de papel, mas será necessário incluir esses dados no novo sistema.

 Os pacientes também precisam de cadastro, contendo dados pessoais (nome, data de nascimento, endereço, telefone e e-mail), documentos (CPF e RG) e convênio. Para cada convênio, são registrados nome, CNPJ e tempo de carência.

 As consultas também têm sido registradas em planilhas, com data e hora de realização, médico responsável, paciente, valor da consulta ou nome do convênio, com o número da carteira. Também é necessário indicar na consulta qual a especialidade buscada pelo paciente.

 Deseja-se ainda informatizar a receita do médico, de maneira que, no encerramento da consulta, ele possa registrar os medicamentos receitados, a quantidade e as instruções de uso. A partir disso, espera-se que o sistema imprima um relatório da receita ao paciente ou permita sua visualização via internet.

 **Exemplo de Requisitos do Banco de Dados:**

 A coleção de médicos, por exemplo, teria suas características definidas como segue:

 - `_id` (ObjectId)
 - `nome` (String)
 - `data_nascimento` (Date)
 - `especialidades` (Array de Strings) - Ex.: ["Pediatria", "Clínica Geral"]
 - `tipo` (String) - Ex.: "Generalista", "Especialista", "Residente"
 - `contato`: { `telefone` (String), `email` (String) }
 - `documentos`: { `CPF` (String), `RG` (String) }

📌 **Tarefa:** Crie o modelo do banco de dados com base na descrição acima.

---

## Parte 2 - Não era exatamente assim

Considere a seguinte descrição:

 No hospital, as internações têm sido registradas por meio de formulários eletrônicos que gravam os dados em arquivos.

 Para cada internação, são anotadas a data de entrada, a data prevista de alta e a data efetiva de alta, além da descrição textual dos procedimentos a serem realizados.

 As internações precisam ser vinculadas a quartos, com a numeração e o tipo.

 Cada tipo de quarto tem sua descrição e o seu valor diário (a princípio, o hospital trabalha com apartamentos, quartos duplos e enfermaria).

 Também é necessário controlar quais profissionais de enfermaria estarão responsáveis por acompanhar o paciente durante sua internação. Para cada enfermeiro(a), é necessário nome, CPF e registro no conselho de enfermagem (COREN).

 A internação, obviamente, é vinculada a um paciente – que pode se internar mais de uma vez no hospital – e a um único médico responsável.

📌 **Tarefa:** Modele os dados de internação conforme a descrição.

---

## Parte 3 - Jogando nas regras que você criou

Crie scripts de povoamento dos documentos desenvolvidos na atividade anterior.

📌 **Atividades obrigatórias:**

- [x] Inclua ao menos 12 médicos de diferentes especialidades.
- [x] Ao menos sete especialidades (ex.: Pediatria, Clínica Geral, Gastroenterologia, Dermatologia).
- [x] Inclua ao menos 15 pacientes.
- [x] Registre 20 consultas de diferentes pacientes e diferentes médicos.
  - [x] Alguns pacientes devem realizar mais de uma consulta.
  - [x] As consultas devem ter ocorrido entre 01/01/2015 e 01/01/2022.
  - [x] Pelo menos 10 consultas devem ter receituário com dois ou mais medicamentos.
- [x] Relacione as internações com IDs de médicos e pacientes.
- [x] Registre ao menos 7 internações.
  - [x] Pelo menos 2 pacientes devem ter se internado mais de uma vez.
  - [x] Pelo menos 3 quartos devem ser cadastrados.
  - [x] As internações devem ter ocorrido entre 01/01/2015 e 01/01/2022.
- [x] Inclua os tipos de quarto: apartamento, quarto duplo e enfermaria, com valores diferentes.
- [x] Inclua dados de 10 profissionais de enfermaria.
- [x] Associe cada internação a pelo menos 2 enfermeiros.
- [x] Os dados de tipo de quarto, convênio e especialidade devem ser povoados no início do sistema.

---

## Parte 4 - Inserindo Dados

Pensando no banco que já foi criado para o Projeto do Hospital, realize algumas alterações nas coleções e nos dados usando comandos de **atualização e exclusão**:

📌 **Tarefas:**

- [ ] Crie um script que adicione uma coluna `em_atividade` para os médicos, indicando se ele ainda está atuando no hospital ou não.
- [ ] Crie um script para atualizar ao menos dois médicos como **inativos** e os demais como **em atividade**.

---

## Parte 5 - Consultas para que te quero

Crie um script e nele inclua **consultas que retornem** os seguintes dados (responda abaixo em JSON):

### 1. Todos os dados e o valor médio das consultas do ano de 2020 e das que foram feitas sob convênio.

```json
{

}
```

### 2. Todos os dados das internações que tiveram data de alta maior que a data prevista para a alta.

```json
{

}
```

### 3. Receituário completo da primeira consulta registrada com receituário associado.

```json
{

}
```

### 4. Todos os dados da consulta de maior valor e também da de menor valor (ambas as consultas não foram realizadas sob convênio).

```json
{

}
```

### 5. Todos os dados das internações em seus respectivos quartos, calculando o total da internação a partir do valor de diária do quarto e o número de dias entre a entrada e a alta.

```json
{

}
```

### 6. Data, procedimento e número de quarto de internações em quartos do tipo “apartamento”.

```json
{

}
```

### 7. Nome do paciente, data da consulta e especialidade de todas as consultas em que os pacientes eram menores de 18 anos na data da consulta e cuja especialidade não seja “pediatria”, ordenando por data de realização da consulta.

```json
{

}
```

### 8. Nome do paciente, nome do médico, data da internação e procedimentos das internações realizadas por médicos da especialidade “gastroenterologia”, que tenham acontecido em “enfermaria”.

```json
{

}
```

### 9. Os nomes dos médicos, seus CRMs e a quantidade de consultas que cada um realizou.

```json
{

}
```

### 10. Todos os médicos que tenham "Gabriel" no nome.

```json
{

}
```

### 11. Os nomes, CORENs e número de internações de enfermeiros que participaram de mais de uma internação.

```json
{

}
```

---
📎 **Importante:** Utilize sempre o padrão de modelagem NoSQL orientado a documentos (MongoDB) e utilize referências (`ObjectId`) quando necessário entre coleções (ex.: pacientes, médicos, quartos, etc.).

🧪 Este repositório deve conter scripts e exemplos para fins de testes, aprendizado e desenvolvimento.

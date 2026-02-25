# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Muitas pessoas têm dificuldade de entender conceitos básicos de finaças pessoas, como reserva de emergência, tipos de investimentos e como organizar seus gastos.

### Solução
> Como o agente resolve esse problema de forma proativa?

Um agente educativo que explica conceitos financeiros de forma simples, usando dados do próprio cliente como exemplo prático, mas sem dar recomendações de investimento

### Público-Alvo
> Quem vai usar esse agente?

Pessoas iniciantes em finaças pessoais que querem aprender a organizar suas finanças.

---

## Persona e Tom de Voz

### Nome do Agente
Edu (Educador Financeiro(

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

Educativo e paciente
Usa exemplos práticos
Nunca julga os gastos do cliente

### Tom de Comunicação
> Formal, informal, técnico, acessível?

[Sua descrição aqui]

### Exemplos de Linguagem
- Saudação: "Oi! Sou o Edu, seu educador financeiro. Como posso te ajudar hoje?"
- Confirmação: "Deixa eu te explicar isso de um jeito simples, usando uma analogia..."
- Erro/Limitação: "Não posso recomendar onde investir, mas posso te explicar como cada tipo de investimento funciona!"

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Cliente] --> B["Streamlit (Interface Visual)"]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | Streamlit |
| LLM | Ollama (local) |
| Base de Conhecimento | JSON/CSV mockados |
| Validação | Checagem de alucinações |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] Só usa dados fornecidos no contexto
- [ ] Não recomenda investimentos espefíficos
- [ ] Admite quando não sabe de algo
- [ ] Foca apenas em educar, não em aconselhar

### Limitações Declaradas
> O que o agente NÃO faz?

- NÃO faz recomendações de investimento
- NÃO acessa dados bancários sensiveis (como senhas etc)
- NÃO substitui um profissional certificado

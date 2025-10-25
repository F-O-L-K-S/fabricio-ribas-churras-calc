# ChurrasCalc Console 🔥

## 🎯 Objetivo

Ensinar **JavaScript com Node** por meio de uma **aplicação console** que:

- Gerencia convidados (CRUD simples)
- Configura regras (quantidades por pessoa, arredondamentos)
- Calcula plano (carnes, bebidas, gelo, carvão)
- Divide custos (igual, por consumo, ponderado)
- Exporta um resumo (JSON/Markdown/CSV)

---

## 🗺️ Roadmap em 4 Etapas

### Etapa 1 — Base do Console + Loop principal

**Meta:** subir app console com menu interativo e persistência em JSON.

**Entregas**
- Node (ESM: `"type": "module"`).
- Loop principal com menu (ex.: `prompts` ou `readline` nativo).
- Persistência local em `.churras/data.json`.

**Telas**
- [1] Listar convidados
- [2] Adicionar convidado
- [0] Sair

**Critérios de aceite**
- Abrir o app → navegar pelas opções → adicionar/listar salvando em arquivo.
- Tratamento básico de erro (inputs vazios, duplicados).

---

### Etapa 2 — Configuração & Regras

**Meta:** permitir editar parâmetros do cálculo (ex.: carne/adulto).

**Entregas**
- `.churras/config.json` com defaults:
  - Carne/adulto = **400 g**; criança = **200 g**
  - Cerveja/bebedor = **6 latas (350 ml)**
  - Refrigerante/pessoa = **600 ml**
  - Carvão = **1,3 kg / 5 pessoas**
  - Gelo = **5 kg / 10 pessoas**
  - Proporção carnes: **50% bovino, 25% frango, 25% linguiça**
  - Tolerância **+10%** (opcional)

**Tela**
- [3] Configurações (ver e editar)

**Critérios de aceite**
- Alterar um parâmetro e ver refletido no plano (Etapa 3).

---

### Etapa 3 — Cálculo do Plano & Export

**Meta:** consolidar lógica de domínio e saída “bonita” no terminal.

**Entregas**
- **Tela:**
  - [4] Calcular Plano do Evento
    - Mostra totais (adultos/crianças/bebedores)
    - Tabela: bovino/frango/linguiça (kg), cerveja (latas), refri (L), carvão (kg), gelo (kg)
  - [5] Exportar Plano (JSON/Markdown/CSV)
- Arredondamentos “por packs” (12 latas, saco 5 kg, etc.).

**Critérios de aceite**
- Plano faz sentido com diferentes conjuntos de convidados.
- Exports gerados corretamente na pasta `.churras/exports`.

---

### Etapa 4 — Custos & Divisão

**Meta:** praticar coleções, agregações e patterns (Strategy).

**Entregas**
- `.churras/prices.json` (preço por item, ex.: `carne.bovino`, `cerveja.lata`).

**Tela**
- [6] Custos (listar/editar preços)
- [7] Dividir Conta
  - Modos: `equal`, `by-drink`, `weighted`
  - Mostrar cotas por convidado + export CSV

**Critérios de aceite**
- Total geral = soma das cotas.
- Mudar o modo altera distribuição de forma coerente.

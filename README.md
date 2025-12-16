# GUI vs Console — Diferenças

![PBI Inventory Framework Versions Infographic](gui_console_versions.png)

---

## 1) Mesma entrega, experiências diferentes
- **As duas versões rodam o mesmo Framework** e entregam o mesmo objetivo: gerar o inventário do Power BI e publicar/organizar no Notion.
- **A diferença real é a experiência de uso e o nível de autonomia exigido do Usuário.**

---

## 2) Para quem é cada versão
### Versão GUI (oficial)
- Feita para **Usuário regular / Operação**.
- O usuário segue um **wizard** e não precisa “saber terminal”.
- Menos chance de erro por caminho/ambiente/config.

### Versão Console (Advanced)
- Feita para **DEVs e Key Users avançados**.
- Exige **Python instalado**, terminal (CMD/PowerShell) e preparo de ambiente (venv + pip).
- Ideal quando a empresa **bloqueia executáveis** (ex.: `inventory_gui.exe`) ou quando o usuário quer **controle fino** do run.

---

## 3) Diferença de fluxo (o que muda na prática)
### GUI
1. O Usuário preenche inputs dentro da aplicação.
2. A GUI padroniza o caminho e conduz a execução.
3. O Usuário acompanha status sem “barulho de terminal”.
4. No final, ele recebe o resumo e os links.

### Console
1. O Usuário prepara tudo “na mão”:
   - instala Python, cria venv, instala dependências
   - edita configs (`pbi_config.json` no projeto; `notion_config.json` e `ai_config.json` no app)
2. Executa o `framework_full.py` por comando.
3. Acompanha o run via saída do terminal e, de preferência, via `run.log`.
4. Se falhar, ele mesmo faz a triagem inicial (dependências, permissões, paths, tokens).

---

## 4) Diferença técnica (nível mais técnico, sem enrolação)
- **GUI** = um “front-end” que reduz risco operacional e padroniza o uso (menos variáveis do ambiente).
- **Console** = execução direta, com mais dependência do ambiente do Windows/Python do Usuário:
  - PATH / pip / venv
  - permissões de pasta
  - política do PowerShell (execution policy)
  - libs instaladas
- Console também facilita **debug** e **automação** (ex.: rodar em pipelines internos) porque o comando pode ser repetido e logado.

---

## 5) Resumo executivo (1 frase)
**GUI é o caminho oficial para operação sem atrito; Console é o plano para ambientes bloqueados e para Usuários avançados que precisam de controle e debug.**

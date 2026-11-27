# Plano de Ação — Demandas UNIFACC

Sistema web para **elaborar, numerar e acompanhar demandas e projetos institucionais** da UNIFACC, com plano de ação no formato **5W2H**, categorias, dimensões estratégicas (BSC) e controle de orçamento (STRATEX, CAPEX e OPEX).

É um site estático de um único arquivo (`index.html`), sem servidor e sem instalação.

## Funcionalidades

- **Numeração automática** de projetos (`PRJ-001`, `PRJ-002`…), com prefixo configurável.
- **Plano de ação 5W2H** em todo projeto: O quê, Por quê, Onde, Quando, Quem, Como e Quanto.
- **Indicadores operacionais e metas**: as ações são agrupadas e numeradas por indicador (1.1, 1.2, 2.1…), como no modelo de Planejamento Estratégico.
- **Painel**: progresso médio, ações atrasadas, próximos prazos (30 dias), demandas por categoria, situação, dimensões do BSC e orçamento por tipo de despesa.
- **Quadro (kanban)**: arraste os cartões para mudar a situação (Planejamento, Em execução, Em validação, Concluído, Suspenso).
- **Lista** com ordenação, busca e filtros (categoria, situação, dimensão e prioridade).
- **Cronograma (Gantt)** dos projetos, com expansão das ações e marcação de “hoje”.
- **Ficha do projeto**: dimensão estratégica, objetivo, indicador, meta, líder, áreas envolvidas, período, orçamento aprovado × planejado nas ações, entregas.
- **Acompanhamento**: histórico automático de mudanças e registro de atualizações.
- **Categorias** editáveis (nome e cor).
- **Exportação**: lista e plano de ação em CSV (abre no Excel), impressão/PDF da ficha, backup completo em JSON.
- Modo claro e escuro automático; funciona no celular.

## Como publicar no GitHub Pages

1. Envie `index.html` e este `README.md` para a raiz do repositório.
2. No GitHub, abra **Settings → Pages**.
3. Em **Build and deployment**, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)` e clique em **Save**.
4. Em alguns minutos o site estará em `https://languagestructure.github.io/plano_de_acao/`.

Para testar localmente, basta abrir o `index.html` no navegador.

## Onde ficam os dados

Os dados são salvos no **navegador de quem usa** (localStorage). Isso significa que:

- cada computador/navegador tem sua própria base;
- limpar os dados do navegador apaga as demandas.

Por isso, use **Categorias e dados → Exportar backup (JSON)** com frequência. O backup pode ser importado em outro computador.

Para que toda a equipe veja e edite **a mesma base em tempo real**, o próximo passo é ligar o site a um banco de dados em nuvem (por exemplo, Firebase ou Supabase). A camada de dados está concentrada nas funções `load()` e `save()` do `index.html`, o que facilita essa troca.

## Cores e tipografia

- Azul UNIFACC `#173F7A`, marinho `#0A2255`, dourado `#F9A51A` (cores do site unifacc.com.br)
- Fonte: Montserrat (Google Fonts)

## Projetos de exemplo

Na primeira abertura, o botão **Carregar projetos de exemplo** cria quatro demandas, incluindo o *Projeto 1750 — Ampliar a base de alunos*, com os planos de ação do material de Planejamento Estratégico para Instituições Educacionais. Edite ou exclua à vontade.

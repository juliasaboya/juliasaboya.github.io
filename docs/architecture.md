# Arquitetura

Todos os arquivos de páginas, estilos, scripts e dados foram criados vazios de propósito. O objetivo desta etapa foi apenas deixar o repositório pronto para crescer com organização.

## Visão geral

```text
/
|-- index.html
|-- 404.html
|-- .nojekyll
|-- sobre/
|-- projetos/
|   |-- index.html
|   |-- aplicacoes-mobile/
|   |-- aplicacoes-web/
|   |-- aplicacoes-embarcadas/
|   |-- machine-learning-ia/
|   |-- sistemas-distribuidos/
|   `-- ...
|-- experiencias/
|-- curriculo/
|-- contato/
|-- artigos/
|-- components/
|-- assets/
|-- data/
|-- docs/
`-- scripts/
```

## Responsabilidade de cada pasta

- `/`: ponto de entrada do site e rotas estáticas principais do portfólio.
- `/sobre`, `/experiencias`, `/curriculo`, `/contato`, `/artigos`: cada seção pública possui sua própria rota com `index.html`.
- `/projetos`: entrada da área de projetos. O primeiro nível é organizado por categoria de conteúdo; dentro de cada categoria entrarão as páginas individuais de cada projeto.
- `/components/layout`: fragmentos reutilizáveis de estrutura global, como `head`, header e footer.
- `/components/ui`: fragmentos reutilizáveis de interface, como cards e itens de listagem.
- `/assets/css/base`: fundação visual global, incluindo reset, variáveis, tipografia e utilitários.
- `/assets/css/layout`: regras estruturais compartilhadas entre várias páginas.
- `/assets/css/components`: estilos isolados por componente reutilizável.
- `/assets/css/pages`: estilos específicos por rota ou por template de detalhe.
- `/assets/js/core`: inicialização da aplicação e utilitários centrais.
- `/assets/js/modules`: comportamentos reutilizáveis entre páginas.
- `/assets/js/pages`: scripts específicos por página ou tipo de detalhe.
- `/assets/media`: imagens, ícones, documentos e favicons.
- `/data/site`: dados globais do site, como navegação, links sociais e SEO.
- `/data/home`, `/data/sobre`, `/data/experiencias`, `/data/curriculo`, `/data/contato`, `/data/artigos`: conteúdo estruturado por domínio.
- `/data/projetos`: índice geral da área e subpastas por categoria. Cada categoria já possui seu próprio `index.json` e poderá receber arquivos dedicados por projeto depois.
- `/docs`: documentação técnica curta do repositório.
- `/scripts`: espaço reservado para automações futuras, como sitemap, RSS e geração de índices.

## Decisões de escalabilidade

1. Cada rota pública já possui espaço para CSS e JS dedicados.
2. A área de projetos começa por categoria em `/projetos/<categoria>/` e pode evoluir para `/projetos/<categoria>/<slug>/` sem quebrar a navegação principal.
3. Os dados acompanham essa mesma estrutura em `/data/projetos/<categoria>/`, o que reduz acoplamento entre listagem, filtros e páginas internas.
4. Componentes reutilizáveis foram separados da camada de páginas para reduzir repetição quando o portfólio crescer.
5. Conteúdo estruturado foi separado da apresentação para facilitar manutenção e futura migração para outra stack.
6. A estrutura suporta expansão para dezenas de projetos e artigos sem exigir reorganização profunda.

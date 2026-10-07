# Economiza AI

Comparador de preços com IA focado em encontrar e destacar menores ofertas dentro do próprio aplicativo.

## Como funciona

1. O cliente informa o produto.
2. O servidor consulta fontes de preços estruturadas (Mercado Livre API/web e Zoom).
3. As ofertas são filtradas para reduzir acessórios e produtos incompatíveis.
4. Os resultados são deduplicados e ranqueados pelo preço/condição.
5. O cliente recebe a melhor oferta e links de produto quando uma URL direta é validada.

**Importante:** o aplicativo não faz pesquisa web genérica em Google, Bing, DuckDuckGo ou Yahoo e não redireciona a pesquisa do usuário para esses buscadores.

## Render

O projeto inclui `Dockerfile`, `render.yaml`, `requirements.txt` e `start_servidor.sh`.

- Porta: definida pela variável `PORT` do Render.
- Health check: `/api/health`.
- Endpoint de comparação: `/api/search?q=...`.
- Endpoint do agente: `/api/agent?q=...`.
- `/api/web-search` permanece apenas como resposta 410 para impedir chamadas antigas; ele não executa pesquisa.

## GitHub

Suba o conteúdo da pasta `economiza_ai_github/` para o repositório.

## Variáveis opcionais

- `ALLOWED_ORIGIN`: origem permitida para CORS.
- `ADMIN_API_TOKEN`: protege endpoints administrativos de aprendizado/checkpoint.

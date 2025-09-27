# 🌟 Kong Gateway Workshop - Projetos Evolutivos

Este workshop apresenta Kong Gateway através de projetos progressivos, desde conceitos fundamentais até plugins avançados multi-linguagem.

## 🎯 Visão Geral

Demonstração prática e evolutiva do Kong Gateway, explorando desde proxy básico até desenvolvimento de plugins customizados, culminando com uma análise técnica sobre **por que Lua é escolhido** para embedding em sistemas como Kong.

## 📊 Estrutura dos Projetos

### 🎢 Progressão de Aprendizado

```text
Básico (01-04)      → Avançado (05-07)    → Observabilidade
      ↓                      ↓                      ↓
Proxy/Auth/Rate/LB   Plugins/Transform     Métricas/Grafana
```

### 📚 Projetos do Workshop

| # | Projeto | Conceito Principal | Tecnologias | Duração |
|---|---------|-------------------|-------------|---------|
| **01** | **[Proxy Básico](./01-basic-proxy/)** | Kong como reverse proxy | Kong + nginx | 5min |
| **02** | **[Load Balancing](./02-load-balancing/)** | Distribuição de carga | Kong + multi-upstream | 10min |
| **03** | **[Autenticação](./03-authentication/)** | Key Auth + JWT | Kong + Auth plugins | 8min |
| **04** | **[Rate Limiting](./04-rate-limiting/)** | Controle de tráfego | Kong + Redis | 7min |
| **05** | **[Transformações](./05-transformations/)** | Request/Response transform | Kong + transform plugins | 8min |
| **06** | **[Plugin Customizado](./06-custom-plugin/)** | Plugin Lua personalizado | Lua + Kong PDK | 15min |
| **07** | **[Métricas & Observability](./07-metrics/)** | Monitoramento completo | Prometheus + Grafana | 12min |

> ⏱️ **Duração total estimada**: ~1h5min

## 🧪 Coleção de Testes - Bruno

O projeto inclui uma coleção organizada de requisições HTTP usando **Bruno** para facilitar os testes:

```text
_bruno/kong/
├── 01 - Base requests/     # Status, serviços, headers
├── 02 - Load balancer/     # Testes de distribuição de carga  
├── 03 - auth/              # Autenticação e tokens
├── 04 - rate limit/        # Limites de taxa
├── 05 - transformation/    # Transformações de dados
└── 06 - lua plugin/        # Plugins customizados
```

### Como usar a coleção Bruno

1. **Instalar Bruno**: [Download oficial](https://www.usebruno.com/)
2. **Abrir coleção**: File → Open Collection → `_bruno/kong`
3. **Executar projeto**: `docker-compose up -d` no diretório desejado
4. **Testar endpoints**: Usar as requisições organizadas por funcionalidade

## 🚀 Execução Rápida

### Demonstração Completa (Automática)

```bash
./demo-all.sh
```

### Projeto Individual

```bash
cd <projeto-desejado>
docker-compose up -d
# Seguir instruções do README.md
docker-compose down -v
```

## 📁 Estrutura dos Projetos

Cada projeto possui:

- `README.md` com explicação detalhada
- `docker-compose.yml` para ambiente isolado  
- `kong.yml` com configuração declarativa
- Scripts de demonstração quando aplicável
- Aplicações mock para teste

## 🚀 Pré-requisitos

- **Docker** e **Docker Compose**
- **Bruno** (opcional, para testes organizados)
- **curl** ou **Postman** (alternativa ao Bruno)
- Editor de código

## 🎯 Objetivos do Workshop

- Entender os conceitos fundamentais do Kong Gateway
- Aprender configurações declarativas vs Admin API  
- Implementar padrões comuns de API Gateway
- Desenvolver plugins customizados em Lua e Go
- Compreender por que Lua é ideal para embedding

## 🎯 Fluxo Sugerido para Apresentação

1. **Básico** (01-04): Proxy, load balancing, auth e rate limiting
2. **Avançado** (05-06): Transformações e plugins customizados em Lua
3. **Observabilidade** (07): Métricas, Prometheus e Grafana
4. **Demo Completa**: Execução com monitoramento em tempo real
5. **Q&A**: Discussão sobre casos de uso reais

## 📖 Documentação Complementar

- **[VISAO-GERAL.md](./docs/VISAO-GERAL.md)** - Visão detalhada de todos os projetos
- **[DOCKER-CLEANUP.md](./docs/DOCKER-CLEANUP.md)** - Guia de limpeza do ambiente Docker
- **[Observabilidade](./docs/)** - Documentação sobre monitoramento e métricas
- **Coleção Bruno** - Requisições organizadas para teste em `_bruno/kong/`
- **READMEs individuais** - Documentação específica de cada projeto

## �️ Ferramentas de Desenvolvimento

### Limpeza do Docker

Para resetar completamente o ambiente Docker durante o desenvolvimento:

```bash
./docker-cleanup.sh          # Limpeza interativa com confirmação
./docker-cleanup.sh --force  # Limpeza automática (sem confirmação)
./docker-cleanup.sh --stats-only  # Apenas visualizar recursos atuais
```

📖 **Documentação completa**: [DOCKER-CLEANUP.md](./docs/DOCKER-CLEANUP.md)

⚠️ **Atenção**: Remove TODOS os recursos Docker do sistema (containers, imagens, volumes, redes)

## �🔗 Links Úteis

- [Kong Gateway Docs](https://docs.konghq.com/gateway/)
- [Kong Plugin Development](https://docs.konghq.com/gateway/latest/plugin-development/)
- [Bruno API Client](https://www.usebruno.com/)
- [Lua Programming Guide](https://www.lua.org/manual/5.1/)

---

**💡 Dica**: Comece pelo projeto `01-basic-proxy` para entender os conceitos fundamentais e siga a progressão numérica para uma experiência de aprendizado estruturada.

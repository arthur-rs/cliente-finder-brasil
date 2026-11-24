# Cliente Finder Brasil

Skill do Claude Code que encontra, com evidência, clientes potenciais no **mercado brasileiro** a partir de sinais públicos: Facebook, Instagram, LinkedIn, YouTube, TikTok, Reclame Aqui, Mercado Livre, Google Maps, X, Reddit BR, fóruns e sites de vagas (Gupy, Catho, InfoJobs).

Fork de [carolinacherry/claude-first-customer-finder-skill](https://github.com/carolinacherry/claude-first-customer-finder-skill) (MIT), adaptado para o Brasil:

- pesquisa em português, com o vocabulário do público ("alguém indica", "socorro", "vale a pena?");
- mapa de fontes fortes no Brasil, B2C e B2B (inclui CNPJ e dados públicos de empresa);
- regras de LGPD (sem dado sensível, sem CPF, sem grupo privado ou de WhatsApp);
- modos novos: **infoproduto** (low ticket por anúncio: frases de dor viram ângulos de criativo) e **local** (Google Maps, grupos de cidade, OLX);
- relatório HTML em português.

Só pesquisa. Nunca envia mensagem, comenta ou contata ninguém.

## Instalar

```bash
git clone https://github.com/arthur-rs/cliente-finder-brasil
node cliente-finder-brasil/scripts/install.js
```

Instala em `~/.claude/skills/cliente-finder-brasil`. Abra uma sessão nova do Claude Code e peça:

> Ache dez clientes potenciais para https://exemplo.com.br

> Modo infoproduto: ache as dores do público do meu PDF para criativos

O relatório precisa de Python 3.9+ (`python3`, ou `py` no Windows).

## Modos

`rápido` · `padrão` · `profundo` · `infoproduto` · `parceiros-de-teste` · `b2b` · `comunidade` · `local`

## Licença

MIT. Créditos do original a Daniel An.

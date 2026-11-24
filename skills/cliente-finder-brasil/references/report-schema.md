# Formato do relatório

O gerador transforma a análise em JSON num relatório HTML único. Escreva o JSON numa pasta temporária e rode (no Windows, `py` no lugar de `python3`):

```bash
python3 scripts/generate_report.py analysis.json outputs/relatorio-clientes.html
```

O script usa só a biblioteca padrão do Python 3.9+. Devolva o caminho absoluto como link clicável. Não cole o JSON na resposta, a menos que o usuário peça os dados brutos. Escreva todos os textos em português do Brasil; as chaves do JSON ficam em inglês.

## Schema

```json
{
  "title": "Primeiros clientes da Exemplo",
  "product": "Example",
  "product_url": "https://example.com",
  "target_customer": "Donos de academia independentes",
  "search_scope": "Fontes públicas em português (Facebook, Instagram, YouTube, Reclame Aqui), últimos 12 meses",
  "generated_at": "2026-07-13",
  "mode": "padrão",
  "verdict": "Um parágrafo curto dizendo onde estão os sinais mais fortes e quem lidera a lista. Não comece com sim ou não; a página não mostra pergunta.",
  "prospects": [
    {
      "name": "Academia Exemplo",
      "type": "Empresa",
      "stage": "Consciente do problema",
      "score": 82,
      "signal": "O dono contou em público que cobra mensalidade atrasada no WhatsApp, na mão, toda semana.",
      "evidence": "Post recente num grupo público descrevendo o processo e o tempo perdido, em primeira pessoa.",
      "why_fit": "O produto automatiza exatamente a cobrança e o lembrete descritos.",
      "why_now": "O post tem três semanas e pergunta como outros donos resolvem.",
      "source": {
        "title": "Como vocês cobram aluno inadimplente?",
        "url": "https://example.com/public-post",
        "type": "Grupo público do Facebook",
        "date": "2026-06-20"
      },
      "channel": "Responder no próprio post",
      "opener": "Vi sua pergunta sobre cobrança de aluno atrasado...",
      "caution": "Confirme se a cobrança ainda é manual antes de oferecer.",
      "scores": {
        "pain": 5,
        "fit": 5,
        "timing": 4,
        "reachability": 4,
        "evidence": 4
      }
    }
  ],
  "patterns": [
    {
      "title": "Cobrança manual",
      "count": 4,
      "insight": "Os donos caem em planilha e WhatsApp quando o pagamento falha."
    }
  ],
  "outreach_plan": {
    "angle": "Ofereça um teste feito à mão antes de pedir para usar o sistema.",
    "first_step": "Mande para os três de maior nota uma pergunta baseada na fonte.",
    "follow_up": "Mostre uma demo de dois minutos só depois que confirmarem a dor.",
    "success": "Três conversas e um parceiro de teste em sete dias."
  },
  "limits": [
    "Clientes potenciais inferidos de sinais públicos, não compradores confirmados.",
    "Confira se cada sinal ainda é atual antes de abordar; todo contato é manual."
  ]
}
```

## Regras

- Modo `padrão`: até 10 prospects. `rápido`: até 5. `profundo`: até 20. `infoproduto`: até 10 comunidades/publicações, com `opener` = ângulo de criativo e `patterns` = ângulos de anúncio.
- Todo prospect precisa de `source.url` real e verificada (http/https) e de `score` 0–100 coerente com `scores`.
- As chaves de `scores` são `pain`, `fit`, `timing`, `reachability`, `evidence`, cada uma 0–5. Use `stage` em português ("Alta intenção", "Consciente do problema", "Gatilho presente").
- Campos opcionais vazios têm padrão seguro; não invente texto para preencher.

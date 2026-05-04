#  Crime Estimator SP

Estimador de criminalidade por bairro e município do Estado de São Paulo, baseado nos índices oficiais da SSP-SP (2024/2025).

Sem downloads, sem dependências externas — apenas Java puro.

## Como usar

```bash
javac CrimeEstimator.java
java CrimeEstimator
```

Digite o nome do bairro ou município quando solicitado. A busca é parcial — `PINH` encontra `PINHEIROS`, `SÃO BER` encontra `SÃO BERNARDO`, etc.

## Exemplo de saída

```
╔══════════════════════════════════════════════╗
║  Estimador de Criminalidade - SP (SSP 2025) ║
╚══════════════════════════════════════════════╝

Digite o nome do bairro ou município: PINHEIROS

══════════════════════════════════════════════
 Localidade : PINHEIROS
 Score      : 410 / 700
 Nível      : 🟠 ALTO
 Contexto   : Roubo de celular alto; zona comercial movimentada
──────────────────────────────────────────────
 Fonte: SSP-SP Estatísticas 2024/2025
══════════════════════════════════════════════
```

## Níveis de risco

| Score     | Nível       |
|-----------|-------------|
| < 100     | 🟢 BAIXO    |
| 100 – 299 | 🟡 MÉDIO    |
| 300 – 499 | 🟠 ALTO     |
| ≥ 500     | 🔴 MUITO ALTO |

## Cobertura

~100 localidades incluindo:

- **Capital SP** — todos os distritos policiais (zonas norte, sul, leste, oeste e centro)
- **Grande SP** — Guarulhos, Osasco, Diadema, Santo André, São Bernardo, Carapicuíba, Barueri e outros
- **Interior e Litoral** — Campinas, Santos, Guarujá, Ribeirão Preto, São José dos Campos e outros

## Metodologia

O score é uma estimativa ponderada baseada nos índices anuais divulgados pela SSP-SP:

```
score = (furtos × 1) + (roubos × 3) + (homicídios × 5)  por 100k habitantes
```

Fonte dos dados: [SSP-SP Estatísticas 2024/2025](https://www.ssp.sp.gov.br/estatistica)

## Requisitos

- Java 11+
- Nenhuma dependência externa

## Licença

MIT

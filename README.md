# norte-dados

Coleta diária das observações GNSS das estações (ITAI, PRCV, MSMN, STHA, GUAI), validação e cálculo dos índices ionosféricos e troposféricos (TEC, ROT, ROTI, gradientes, ZTD, IWV, PWV). Alimenta as APIs que o portal consulta.

| | |
| --- | --- |
| Responsável | time `dados` |
| Executa em | Windows Server na AWS (EC2), uma vez por dia |
| Situação | repositório novo; recebe o pipeline Python que hoje roda no servidor sem git |

## Rodar localmente

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env   # preencher
```

## O que não entra no git

Dados brutos, séries calculadas e qualquer credencial. Os dados ficam no S3; aqui fica só o código e o caminho de onde lê e onde grava.

## Pastas

- `docs/`: fontes, formato das saídas (ver o contrato em `norte-documentacao`), decisões
- `tests/`: testes (`pytest`)

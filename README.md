# Química em Foco — Vercel + PostgreSQL

Sistema web em Flask para acompanhamento de notas, avaliações, frequência, conteúdos e evolução dos estudantes.

## Stack

- Python + Flask
- SQLAlchemy
- PostgreSQL (produção)
- SQLite opcional apenas para desenvolvimento local
- Vercel para hospedagem

## Rodar localmente

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
python app.py
```

Sem `DATABASE_URL`, o projeto usa `quimica.db` localmente.

Para testar com PostgreSQL, defina `DATABASE_URL` antes de iniciar.

## Deploy na Vercel

1. Suba este projeto para o GitHub.
2. Importe o repositório na Vercel.
3. Em **Settings → Environment Variables**, crie:
   - `DATABASE_URL` = URL do seu PostgreSQL
   - `SECRET_KEY` = chave aleatória longa
4. Faça o redeploy.

O Flask é detectado pela Vercel sem uma configuração especial de roteamento. O projeto usa Python 3.12+ e funciona com o runtime Python suportado pela Vercel.

## Banco PostgreSQL

O schema é criado automaticamente na primeira inicialização da aplicação. Os dados ficam no PostgreSQL, não no filesystem da função da Vercel.

**Importante:** antes de usar em produção com dados reais, faça backup do banco e troque a chave secreta padrão.

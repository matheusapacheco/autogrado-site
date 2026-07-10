# Site Autogrado — deploy automático

Este repositório é o site da Autogrado (`https://autogrado.com.br`).
Sempre que houver uma mudança na branch `main`, o GitHub publica sozinho
no Hostinger via FTP (arquivo `.github/workflows/deploy.yml`).

## Como funciona o fluxo
1. O ajuste é feito nos arquivos (index.html, assets, etc.).
2. É enviado (commit + push) para a branch `main`.
3. O GitHub Actions envia tudo por FTP para a pasta `public_html` do Hostinger.
4. Em ~1 minuto o site está atualizado no ar.

## Secrets necessários (Settings > Secrets and variables > Actions)
Estes valores ficam guardados com segurança no GitHub e são pegos no
hPanel do Hostinger em **Arquivos > Contas FTP**:

| Secret            | O que é                                             |
|-------------------|-----------------------------------------------------|
| `FTP_HOST`        | Hostname/IP do FTP (ex: `ftp.autogrado.com.br`)     |
| `FTP_USERNAME`    | Usuário do FTP                                       |
| `FTP_PASSWORD`    | Senha do FTP                                         |
| `FTP_PORT`        | Porta (normalmente `21`)                             |
| `FTP_SERVER_DIR`  | Caminho de destino (ex: `/public_html/`)             |

## Publicar manualmente (opcional)
Aba **Actions** do repositório > workflow "Publicar site no Hostinger" >
botão **Run workflow**.

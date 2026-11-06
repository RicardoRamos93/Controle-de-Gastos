# Controle de gastos

Site pessoal para registrar gastos, contas fixas, parcelas e dívidas, com previsão dos próximos meses.

Tudo roda no navegador. Não há servidor nem banco de dados: os gastos ficam salvos no próprio aparelho (localStorage), e podem ser protegidos com senha e criptografia AES-256.

## Arquivos

| Arquivo | Para que serve |
|---|---|
| `index.html` | O sistema inteiro (tela, estilos e lógica) |
| `manifest.json` | Permite instalar o site como app no celular |
| `sw.js` | Faz o site abrir mesmo sem internet |
| `icon.svg`, `icon-192.png`, `icon-512.png` | Ícones do app |
| `.nojekyll` | Diz ao GitHub Pages para publicar os arquivos como estão |

## Como publicar no GitHub Pages

1. Crie uma conta em https://github.com, se ainda não tiver.
2. Clique em **New repository**. Dê um nome, por exemplo `gastos`, e crie.
3. Na página do repositório, clique em **Add file > Upload files**, arraste todos os arquivos desta pasta (inclusive o `.nojekyll`) e clique em **Commit changes**.
4. Vá em **Settings > Pages**. Em **Branch**, escolha `main` e a pasta `/ (root)`, e clique em **Save**.
5. Depois de um ou dois minutos, o endereço aparece no topo dessa página, algo como `https://seu-usuario.github.io/gastos/`.

Dica: o `.nojekyll` começa com ponto e pode ficar oculto no seu computador. Se ele não for enviado, o site funciona do mesmo jeito.

## Sobre privacidade

- **O código do site é público, os seus dados não.** No plano gratuito, o GitHub Pages exige repositório público, então qualquer pessoa com o link vê a página vazia. Os gastos nunca saem do seu navegador e não vão para o GitHub.
- **Use a senha.** Em *Dados e segurança > Proteger com senha*, os dados passam a ser guardados criptografados. Sem a senha ninguém abre, nem quem pegar o seu aparelho.
- **Se esquecer a senha, não há recuperação.** Guarde backups.
- O site tem `noindex`, então não deve aparecer no Google.

## Usando em mais de um aparelho

Cada navegador tem os próprios dados. Para levar para outro aparelho, use *Baixar backup* em um e *Restaurar backup* no outro. Faça backups de vez em quando: limpar os dados do navegador apaga os gastos.

## Instalar no celular

Abra o endereço no celular e escolha **Adicionar à tela de início** (Safari, no iPhone) ou **Instalar app** (Chrome, no Android). Ele abre como um aplicativo e funciona offline.

## Atualizar o site

Edite os arquivos no GitHub (ou envie novas versões) e aumente o número em `const CACHE = "gastos-v1"` no `sw.js`, para os aparelhos baixarem a versão nova.

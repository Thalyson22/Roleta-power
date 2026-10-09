# Roleta Power NutriFit · Ação 10/10

Site de uma página com uma roleta premiada para a ação de 10/10 da Power NutriFit.
Tudo fica no arquivo `index.html`: não precisa instalar nada nem ter servidor.

## Como funciona

1. O cliente digita o nome e tem **3 giros**. Ele leva os 3 prêmios, e cada giro tira um prêmio diferente.
2. A cada giro aparece o prêmio e o botão **Girar de novo**. As fatias já ganhas ficam apagadas na roleta.
3. No fim aparece o resumo com os 3 prêmios, um código único (ex.: `PWR1010-K7QX`) e o botão **Resgatar no WhatsApp**.
4. O botão abre o WhatsApp da Power com a mensagem pronta (nome, os 3 prêmios, código e regras).
5. Cada aparelho participa uma vez. Quem sai no meio continua de onde parou; quem volta depois vê os prêmios que ganhou.
   O prêmio é salvo no começo de cada giro, então recarregar a página no meio do giro não dá uma nova chance.

> O limite de 1 participação (3 giros) fica salvo no navegador. Quem limpar os dados ou usar aba anônima consegue participar de novo,
> então confira no atendimento: **1 participação por número de WhatsApp**.

## O que editar (no começo do `<script>` do `index.html`, bloco `CONFIG`)

| Campo | O que é |
|---|---|
| `whatsapp` | Número da Power só com dígitos, com 55 + DDD. Ex.: `"5511987654321"` |
| `premios` | Lista de prêmios: `titulo` (ex.: `10% OFF`), `tituloRoleta` (opcional, texto grande da fatia), `textoRoleta` (texto curto da fatia), `detalhe` (onde vale), emoji, `tipo` (`desconto`, `brinde` ou `tente`) e `chance` |
| `giros` | Giros por cliente (hoje 3). Os prêmios não se repetem |
| `fatiasPorPremio` | Quantas vezes cada item aparece na roleta (hoje 2, ou seja, 8 fatias) |
| `abreEm` / `encerraEm` | Opcional: horários para a roleta abrir e fechar sozinha. Hoje os dois estão `null`, ou seja, a roleta fica sempre aberta. Se usar `encerraEm`, depois dele aparece "Ação encerrada" (quem já tinha girado continua vendo os prêmios) |
| `REGRAS` | Textos da seção "Regras da ação" |

As cores ficam no topo do `<style>`, em `:root` (`--brand`, `--gold` etc.).

### Prêmios atuais

Com 3 giros sem repetir e 3 prêmios sorteáveis, todo cliente ganha os 3 prêmios (a ordem é que muda).
Se dois descontos valerem para o mesmo produto, vale o maior (eles não se somam).

| Prêmio | Onde vale | Fatias |
|---|---|---|
| 15% OFF | Todos os produtos Evorox (na compra atual) | 2 |
| 20% OFF | Kit com 1 produto Evorox + 1 produto de qualquer outra marca (na compra atual) | 2 |
| Brinde especial | Compras acima de R$ 100,00 | 2 |
| Não foi dessa vez | Só enfeite: aparece na roleta, mas **nunca é sorteado** (`tipo: "tente"`) | 2 |

## Testar

Abra o `index.html` no navegador. Para girar de novo no mesmo aparelho, coloque `?reset=1` no fim do endereço.

## Publicar (GitHub Pages, grátis)

1. No GitHub, abra **Settings → Pages**.
2. Em **Build and deployment**, escolha **Deploy from a branch**, selecione a branch e a pasta `/ (root)`, e clique em **Save**.
3. Em 1 ou 2 minutos o link fica disponível (algo como `https://thalyson22.github.io/roleta-power/`).

Outra opção é arrastar o `index.html` para o [Netlify Drop](https://app.netlify.com/drop).

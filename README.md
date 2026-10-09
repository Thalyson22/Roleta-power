# Roleta Power NutriFit · Ação 10/10

Site de uma página com uma roleta premiada para a ação de 10/10 da Power NutriFit.
Tudo fica no arquivo `index.html`: não precisa instalar nada nem ter servidor.

## Como funciona

1. O cliente digita o nome e gira a roleta. Todo giro ganha um prêmio.
2. Aparece o prêmio com um código único (ex.: `PWR1010-K7QX`) e o botão **Resgatar no WhatsApp**.
3. O botão abre o WhatsApp da Power com a mensagem pronta (nome, prêmio, código e regra).
4. Cada aparelho gira só uma vez. Quem volta ao site vê o prêmio que já ganhou.

> O limite de 1 giro fica salvo no navegador. Quem limpar os dados ou usar aba anônima consegue girar de novo,
> então confira no atendimento: **1 prêmio por número de WhatsApp**.

## O que editar (no começo do `<script>` do `index.html`, bloco `CONFIG`)

| Campo | O que é |
|---|---|
| `whatsapp` | Número da Power só com dígitos, com 55 + DDD. Ex.: `"5511987654321"` |
| `premios` | Lista de prêmios: texto da fatia, nome, emoji, tipo (`desconto` ou `brinde`) e `chance` |
| `valorMinimoBrinde` | Valor mínimo para liberar brindes (hoje `R$ 100,00`) |
| `abreEm` / `encerraEm` | Horários em que a roleta abre e fecha. Depois de `encerraEm` aparece "Ação encerrada" |
| `REGRAS` | Textos da seção "Regras da ação" |

As cores ficam no topo do `<style>`, em `:root` (`--brand`, `--gold` etc.).

### Chances atuais

| Prêmio | Tipo | Chance |
|---|---|---|
| Barrinha de proteína | brinde | 25% |
| 7% de desconto | desconto | 22% |
| 10% de desconto | desconto | 15% |
| 5% de desconto | desconto | 15% |
| Dose de pré-treino | brinde | 12% |
| Coqueteleira | brinde | 6% |
| Termogênico | brinde | 3% |
| 15% de desconto | desconto | 2% |

## Testar

Abra o `index.html` no navegador. Para girar de novo no mesmo aparelho, coloque `?reset=1` no fim do endereço.

## Publicar (GitHub Pages, grátis)

1. No GitHub, abra **Settings → Pages**.
2. Em **Build and deployment**, escolha **Deploy from a branch**, selecione a branch e a pasta `/ (root)`, e clique em **Save**.
3. Em 1 ou 2 minutos o link fica disponível (algo como `https://thalyson22.github.io/roleta-power/`).

Outra opção é arrastar o `index.html` para o [Netlify Drop](https://app.netlify.com/drop).

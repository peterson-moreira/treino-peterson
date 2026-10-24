# Treino Peterson

Página de registro de treino. Abre no celular, registra a nota de cada exercício
por voz ou por toque, lê o arquivo `.tcx` do relógio e monta o relatório da sessão.

## Por que GitHub Pages

A versão publicada como artifact do Claude não consegue usar o microfone do navegador:
a plataforma bloqueia o acesso ao dispositivo. Servida por aqui, em origem HTTPS própria,
o reconhecimento de fala do Chrome funciona, e o botão **Falar** aparece.

Nos dois casos o ditado do teclado do celular continua funcionando no campo de texto.

## Como publicar

Ative o GitHub Pages em **Settings → Pages**, origem `Deploy from a branch`,
branch `main`, pasta `/ (root)`. A página fica em
`https://<usuario>.github.io/<repositorio>/`.

## Numeração

Os seis treinos e seus exercícios são numerados `bloco.item`:

| Bloco | Treino | Dia |
|---|---|---|
| 1 | Superior A — peito, ombro e tríceps | segunda |
| 2 | Inferior A — quadríceps e posterior | terça |
| 3 | Quarta — HIIT e core | quarta |
| 4 | Superior B — costas, deltoide posterior e bíceps | quinta |
| 5 | Inferior B — posterior e glúteo | sexta |
| 6 | Superior C — peito e bíceps detalhados | sábado |

## Como registrar

Toque num exercício e use o seletor de nota, ou dite a sessão inteira no campo de texto.
O interpretador entende:

- `4.1 8,3 4.2 8 4.3 8,5`
- `quatro ponto um oito vírgula três`
- `4.7 não fiz`
- `1.2 oito e meio`
- só as notas em ordem: `8 8,3 8 8,2` distribui pelos exercícios do bloco

Para exceções, escreva ao lado: carga diferente `(45kg)`, volume diferente `(3x12)`,
exercício trocado `sentado 9kg`.

## Escala de nota

Nota 8 é o alvo: duas repetições na reserva ao fim da série, sem ir à falha técnica.

| Faixa | Leitura |
|---|---|
| abaixo de 8 | estímulo insuficiente, candidato a subir carga |
| 8,0 a 8,4 | no alvo |
| 8,5 a 8,9 | acima do alvo, consolidar antes de progredir |
| 9 ou mais | perto da falha, não progredir |

## Zonas de frequência cardíaca

FCmáx de referência 177 bpm (Tanaka, 208 menos 0,7 vezes a idade).

| Zona | Faixa |
|---|---|
| Z1 | 89 a 105 |
| Z2 | 106 a 123 |
| Z3 | 124 a 141 |
| Z4 | 142 a 158 |
| Z5 | 159 ou mais |

## Dados

Tudo fica no `localStorage` do próprio aparelho. Nada é enviado para servidor nenhum.
O botão **Baixar histórico** exporta um JSON com todas as sessões salvas.

A sessão do dia é guardada automaticamente enquanto você registra; ao trocar de dia
ela é descartada, a menos que tenha sido salva no histórico.

## O que não entra aqui

Este repositório é público, então ele não guarda informação clínica.
Ficam de fora, de propósito: exames, laudos, diagnósticos e pendências
médicas. Esses dados vivem na planilha e na conversa, que são privadas.
O que fica aqui é o programa de treino, as cargas, as notas de
dificuldade e a leitura do TCX do relógio.

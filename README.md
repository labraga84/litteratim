# Litteratim: Jogo com Palavras — listas de palavras e documentos públicos

Este repositório contém:

- **As listas de palavras** usadas pelo jogo *Litteratim: Jogo com Palavras* (Android, LABraga Games),
  publicadas como exigem as licenças livres dos dicionários de onde foram geradas.
- **A Política de Privacidade e os Termos de Utilização** do jogo, na pasta [`docs`](docs)
  (também publicados como página: https://labraga84.github.io/litteratim/).

## Listas de palavras

| Ficheiro | Variante | Palavras |
|---|---|---:|
| [`palavras/pt/palavras-pt_PT.txt`](palavras/pt/palavras-pt_PT.txt) | Português de Portugal | 372 172 |
| [`palavras/pt/palavras-pt_BR.txt`](palavras/pt/palavras-pt_BR.txt) | Português do Brasil | 1 852 795 |
| [`palavras/en/palavras-en.txt`](palavras/en/palavras-en.txt) | English | 171 399 |
| [`palavras/es/palavras-es.txt`](palavras/es/palavras-es.txt) | Español | 580 539 |
| [`palavras/fr/palavras-fr.txt`](palavras/fr/palavras-fr.txt) | Français | 401 972 |

Uma palavra por linha, em maiúsculas, sem acentos, codificação UTF-8. No português o Ç mantém-se e
no espanhol o Ñ mantém-se (são peças do jogo); no francês Œ e Æ passam a OE e AE.
No português, uma palavra válida nas duas variantes aparece nos dois ficheiros.

### Origem

| Variante | Dicionário de origem | Autores | Licença usada |
|---|---|---|---|
| pt_PT | Dicionário pt_PT do Projecto Natura — https://natura.di.uminho.pt | José João Almeida, Rui Vilela, Alberto Simões (Departamento de Informática, Universidade do Minho) | MPL 1.1 (o original é distribuído em GPL 2 / LGPL 2.1 / MPL 1.1) |
| pt_BR | VERO — Verificador Ortográfico do LibreOffice — https://pt-br.libreoffice.org/projetos/projeto-vero-verificador-ortografico/ | Raimundo Santos Moura e equipa | MPL (o original é distribuído em LGPL 3 / MPL) |

| en | ENABLE (Enhanced North American Benchmark Lexicon) — lista `enable1.txt` | Alan Beale, M. Cooper e colaboradores | Domínio público |
| en | SCOWL / dicionário Hunspell en_US — http://wordlist.aspell.net/ | Kevin Atkinson e colaboradores | Licença SCOWL (ver abaixo) |
| es | Diccionario es_ES del proyecto RLA-ES — https://github.com/sbosio/rla-es | Santiago Bosio e colaboradores | MPL 1.1 (o original é distribuído em GPL 3 / LGPL 3 / MPL 1.1) |
| fr | Dictionnaire « Classique » de Grammalecte — https://grammalecte.net/ | Olivier R. e colaboradores | MPL 2.0 |

### Alterações feitas aos dicionários de origem

As listas foram geradas automaticamente a partir dos ficheiros Hunspell (`.dic` + `.aff`) originais:

1. Todas as formas de cada palavra foram geradas a partir das regras de afixos do `.aff`.
2. Foram retiradas:
   - palavras com maiúscula inicial (nomes próprios e siglas);
   - palavras com hífen, ponto, apóstrofo ou outros carateres que não são letras;
   - palavras com K, W ou Y (estrangeirismos, menos de 0,05% das palavras);
   - palavras com menos de 2 ou mais de 15 letras;
   - palavras sem vogais (siglas e unidades, como CM ou ML);
   - no dicionário pt_PT, as entradas marcadas como abreviaturas, numeração romana, pontuação ou
     estrangeirismos;
   - no dicionário pt_BR, algumas regras de afixos que geram formas que não são palavras isoladas
     (radicais de ênclise/mesóclise como "amaremo", aumentativos e diminutivos gerados
     automaticamente) — a lista completa, com o motivo de cada uma, está em
     [`configuracao-pt.json`](palavras/pt/alteracoes/configuracao-pt.json) (secção `dropRules`).
3. Os acentos foram retirados (Á→A, Ê→E, Õ→O, …); o Ç mantém-se.
4. Foram excluídas manualmente as palavras de [`excluidas.txt`](palavras/pt/alteracoes/excluidas.txt)
   (abreviaturas, interjeições, estrangeirismos e restos de regras do corretor) e acrescentadas as de
   [`acrescentadas.txt`](palavras/pt/alteracoes/acrescentadas.txt).

### Inglês, espanhol e francês

O mesmo processo, com a configuração de cada língua em `palavras/<língua>/alteracoes/configuracao-<língua>.json`
e as listas manuais em `excluidas.txt` e `acrescentadas.txt` da mesma pasta. Diferenças:

- **Inglês:** junção da lista ENABLE com todas as formas do dicionário en_US; retiradas as palavras
  marcadas como tabu no SCOWL e insultos; acrescentadas palavras de 2 letras atuais (QI, ZA, OK…)
  e interjeições sem vogal (HMM, SHH…).
- **Espanhol:** retiradas as palavras com K ou W (menos de 0,05% das palavras) e as abreviaturas que o
  corretor aceita (AVD, IZQ, SRA…).
- **Francês:** retiradas as entradas marcadas como símbolos e unidades (flag `||`: KM, YD, PPM…) e
  algumas siglas; formas com apóstrofo (L', D', QU'…) ficam de fora.

## Licença

As listas de palavras são trabalho derivado dos dicionários indicados acima e são distribuídas nos
termos da **Mozilla Public License 1.1** — texto completo em [`LICENSE-MPL-1.1.txt`](LICENSE-MPL-1.1.txt).

> The contents of the word lists in this repository are subject to the Mozilla Public License
> Version 1.1 (the "License"); you may not use these files except in compliance with the License.
> You may obtain a copy of the License at http://www.mozilla.org/MPL/
>
> Software distributed under the License is distributed on an "AS IS" basis, WITHOUT WARRANTY OF
> ANY KIND, either express or implied. See the License for the specific language governing rights
> and limitations under the License.
>
> The Original Code is the pt_PT dictionary of Projecto Natura (Universidade do Minho) and the
> pt_BR dictionary of Projeto VERO (LibreOffice). Modifications: see "Alterações" above.

As listas **en** juntam a ENABLE (domínio público) e o SCOWL, distribuído com esta autorização:

> Copyright 2000-2018 by Kevin Atkinson
>
> Permission to use, copy, modify, distribute and sell these word lists, the associated scripts,
> the output created from the scripts, and its documentation for any purpose is hereby granted
> without fee, provided that the above copyright notice appears in all copies and that both that
> copyright notice and this permission notice appear in supporting documentation. Kevin Atkinson
> makes no representations about the suitability of this array for any purpose. It is provided
> "as is" without express or implied warranty.

A lista **es** é trabalho derivado do RLA-ES, distribuída nos termos da **MPL 1.1**
([`LICENSE-MPL-1.1.txt`](LICENSE-MPL-1.1.txt)).

A lista **fr** é trabalho derivado do dicionário do Grammalecte, distribuída nos termos da
**Mozilla Public License 2.0** ([`LICENSE-MPL-2.0.txt`](LICENSE-MPL-2.0.txt)).

A Política de Privacidade e os Termos de Utilização (pasta `docs`, em português, inglês, espanhol e
francês) não estão abrangidos por estas licenças: © 2026 LABraga Games.

## Contacto

LABraga Games — l.abraga84@gmail.com

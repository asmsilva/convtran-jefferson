# convtran-jefferson

A modified version of Gareth Walker's `convtran.sty` LaTeX package, adapted for **Jefferson (2004) Conversation Analysis transcription conventions**, with particular support for **multilingual transcriptions** (e.g. original utterance + free translation line).

Originally developed for a PhD thesis in Forensic Linguistics on emergency calls, edited in Overleaf.

## Key changes from the original `convtran`

- **Fixed `\tran`, `\glos`, `\phon`**: content is now placed in the item body (aligned with speech text), not in the label column — this was the root cause of misaligned translation lines in multilingual transcriptions.
- **`\tran{}` applies italics automatically**, following Jefferson convention for free translations.
- **`\ob` and `\cb`** — safe overlap brackets that avoid LaTeX optional-argument parsing conflicts with `[` and `]`.
- **New symbols**: `\str{}`, `\smile{}`, `\creak{}`, `\inh`, `\exh`, `\lgh`, `\unclear{}`, `\inaud`, `\loud{}`.

## Usage

Copy `convtran.sty` to your Overleaf project and add `\usepackage{convtran}` to your preamble.

### Basic multilingual excerpt

```latex
\begin{convtran}
\turn{OPE:} Pronto, qui è il centoventidue, \str{prego}?
\tran{Hello, this is one-two-two, how can I help?}
\turn{CAL:} Sì sì, ho bisogno di \ob aiuto,
\tran{Yes yes, I need \ob help,}
\turn{OPE:}                      \cb Dove si trova?
\tran{                           \cb Where are you?}
\turn{CAL:} \q Sono in via Roma \closeq (0.8) c'è un incendio \hl
\tran{\q I'm on via Roma \closeq (0.8) there's a fire}
\end{convtran}
```

## Command reference

### Turn structure

| Command | Function |
|---|---|
| `\turn{FA:}` | Numbered turn with speaker label |
| `\turn*{FA:}` | Unnumbered turn with speaker label |
| `\turn{}` | Numbered line without speaker (pauses, continuations) |
| `\tran{text}` | Free translation (unnumbered, italic, aligned with speech) |
| `\glos{text}` | Morpheme gloss (unnumbered, aligned with speech) |
| `\phon{text}` | Phonetic transcription (unnumbered, aligned with speech) |
| `\info{text}` | Contextual information, e.g. `((shouting))` |

### Overlap

| Command | Symbol | Jefferson convention |
|---|---|---|
| `\ob` | `[` | onset of overlap |
| `\cb` | `]` | offset of overlap |

### Pitch and tempo

| Command | Symbol | Jefferson convention |
|---|---|---|
| `\high` | ↑ | pitch step-up |
| `\low` | ↓ | pitch step-down |
| `>text<` | `>text<` | faster speech (type directly) |
| `<text>` | `<text>` | slower speech (type directly) |

### Volume and emphasis

| Command | Result | Jefferson convention |
|---|---|---|
| `\str{text}` | underlined | primary stress |
| `CAPITALS` | CAPITALS | loud speech (type directly) |
| `\q text \closeq` | °text° | quiet speech |
| `\loud{text}` | bold | very loud (typographic) |

### Voice quality

| Command | Symbol | Jefferson convention |
|---|---|---|
| `\smile{text}` | £text£ | smile voice |
| `\creak{text}` | #text# | creaky voice |

### Breathing and laughter

| Command | Symbol | Jefferson convention |
|---|---|---|
| `\inh` | .hhh | inbreath |
| `\exh` | hhh | outbreath |
| `\lgh` | (h) | laughter token within talk |

### Transcriber markings

| Command | Symbol | Jefferson convention |
|---|---|---|
| `\unclear{text}` | (text) | uncertain hearing |
| `\inaud` | (~~~~~) | inaudible stretch |
| `(0.5)` | (0.5) | timed pause (type directly) |
| `(.)` | (.) | micropause (type directly) |
| `word-` | word- | abrupt cut-off (type directly) |
| `=` | = | latching (type directly) |

### Margin arrows

| Command | Function |
|---|---|
| `\hl` | single arrow → in margin |
| `\Hl` | double arrow ⇒ in margin |
| `\hllab{dist}{label}` | labelled arrow in margin |

## Credits

- Original `convtran.sty`: © 2016–2024 [Gareth Walker](https://github.com/garethwalker), distributed under the [LaTeX Project Public License](http://www.latex-project.org/lppl.txt) v1.3+.
- This modified version: © 2025 Sofia Silva.

## Reference

Jefferson, G. (2004). Glossary of transcript symbols with an introduction. In G. H. Lerner (Ed.), *Conversation analysis: Studies from the first generation* (pp. 13–31). John Benjamins.

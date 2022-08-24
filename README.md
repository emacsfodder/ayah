# Ayah

Ayah provides [auto-yasnippet](https://github.com/abo-abo/auto-yasnippet) with
snippet history features.

- Expand a snippet from history
- Persist a snippet from history

There are additional commands to move through (next/previous) history and delete
a snippet from history.

## Install

_Ayah is pending addition to MELPA._

Install usinng [straight.el](https://github.com/radian-software/straight.el)

```emacs
(straight-use-package
 '(ayah :type git :host github :repo "emacsfodder/ayah"))
```

Install with [Doom](https://github.com/doomemacs) Emacs.

```emacs
(package! ayah :recipe (:host github :repo "emacsfodder/ayah"))
```

# Usage

## ayah-expand-from-history

Select and expand from snippets in `ayah-history`. The selected
snippet will become `aya-current`.

## ayah-next-in-history & ayah-previous-in-history

Set `aya-current` to the next or previous in `ayah-history`.

## ayah-persist-snippet-from-history

Functionally equivalent to `aya-persist-snippet` in but using a snippet selected
from `ayah-history`

## ayah-delete-from-history

Select and delete a snippet from `ayah-history`. The next available
snippet will become `aya-current`. When there are no other snippets
available `aya-current` will be set to `""`.

## ayah-clear-history

Completely clear snippet history (`ayah-history` and  `aya-current` will be cleared).

## Configuration

In your Emacs init file bind keys to the `ayah` commands.

For example:

```emacs
(bind-key "C-c C-y SPC" #'ayah-expand-from-history)
(bind-key "C-c C-y d"   #'ayah-delete-from-history)
(bind-key "C-c C-a n"   #'ayah-next-in-history)
(bind-key "C-c C-a p"   #'ayah-previous-in-history)
(bind-key "C-c C-y s"   #'ayah-persist-snippet)
```

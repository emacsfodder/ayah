# Ayah

Ayah extends [auto-yasnippet](https://github.com/abo-abo/auto-yasnippet) with
snippet history features.

- Expand a snippet from history
- Persist a snippet from history

To manage history there are also commands (next/previous) in history, delete
a snippet from history and clear history.

## Install

_Ayah is pending addition to MELPA._

Install manually. Clone to your machine:

```sh
git clone https://github.com/emacsfodder/ayah
```
Add this to your Emacs init:
```lisp
(add-to-list 'load-path "/path/to/ayah") 
(require 'ayah)
```
- - - 

Install using [straight.el](https://github.com/radian-software/straight.el)

```lisp
(straight-use-package
 '(ayah :type git :host github :repo "emacsfodder/ayah"))
```

Install with [Doom](https://github.com/doomemacs) Emacs.

```lisp
(package! ayah :recipe (:host github :repo "emacsfodder/ayah"))
```
# Setup

The first time you try to access any history features _Ayah_ will hook up to Auto-yasnippet.

To manually initialize call `(ayah-setup)`, for example:

```lisp
(use-package auto-snippet
  :config 
  (require 'ayah)
  (ayah-setup))
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

```lisp
(global-set-key (kbd "C-c C-a SPC") 'ayah-expand-from-history)
(global-set-key (kbd "C-c C-a n") 'ayah-next-in-history)
(global-set-key (kbd "C-c C-a p") 'ayah-previous-in-history)
(global-set-key (kbd "C-c C-a C") 'ayah-clear-history)
(global-set-key (kbd "C-c C-a D") 'ayah-delete-from-history)
(global-set-key (kbd "C-c C-a W") 'ayah-persist-snippet-from-history))
```
You can set the key bindings to those above using:

```lisp
M-x ayah-default-bindings
```

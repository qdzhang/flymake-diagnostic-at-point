# flymake-diagnostic-at-point

Minor mode for showing flymake diagnostics at point.

The diagnostics may be displayed in a childframe(depends on posframe) or in the minibuffer. You may also
provide a custom display function to use instead.

![Flymake diagnostics in a popup](./screenshots/popup.png "Flymake diagnostics in a popup")
![Flymake diagnostics in the minibuffer](./screenshots/minibuffer.png "Flymake diagnostics in the minibuffer")

## Requirement

- [posframe](https://github.com/tumashu/posframe)

## Installation

Save the `.el` file in your Emacs' load path.

## Usage

Add the following to your `init.el`:

``` emacs-lisp
(with-eval-after-load 'flymake
  (require 'flymake-diagnostic-at-point)
  (add-hook 'flymake-mode-hook #'flymake-diagnostic-at-point-mode))
```

Alternatively, if you prefer using `use-package`:

``` emacs-lisp
(use-package flymake-diagnostic-at-point
  :after flymake
  :config
  (add-hook 'flymake-mode-hook #'flymake-diagnostic-at-point-mode))
```

## Customization

There are a few customizable variables:

- `flymake-diagnostic-at-point-timer-delay` controls the delay in seconds before displaying the diagnostics at point
- `flymake-diagnostic-at-point-error-prefix` defines the string to be displayed before each error line (e.g. "➤ ")
- `flymake-diagnostic-at-point-display-diagnostic-function` is the display function to be used. It can be set to `flymake-diagnostic-at-point-display-posframe` to display in a posframe, `flymake-diagnostic-at-point-display-minibuffer` to display in the minibuffer, or any other  function of your choosing that takes a string argument
- `flymake-diagnostic-at-point-posframe-background-face` to customize the background color of the flymake posframe frame. Default uses the background color of `lazy-highlight` face.
- `flymake-diagnostic-at-point-posframe-foreground-face` to customize the foreground color of the flymake posframe frame. Default uses the foreground color of `lazy-highlight` face.

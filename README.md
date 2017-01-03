(setq frame-title-format "emacs")

(menu-bar-mode -1)

(tool-bar-mode -1)

(scroll-bar-mode -1)

(global-linum-mode t)

(add-to-list 'default-frame-alist '(height . 48))

(add-to-list 'default-frame-alist '(width . 165))

(require 'package)

(setq package-archives '(("gnu" . "http://elpa.gnu.org/packages/")
                         ("melpa" . "http://melpa.org/packages/")))
(package-initialize)

(load-theme 'arjen-grey t)

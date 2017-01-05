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

(defun info-mode ()
  (interactive)
  (let ((file-name (buffer-file-name)))
    (kill-buffer (current-buffer))
    (info file-name)))
(add-to-list 'auto-mode-alist '("\\.info\\'" . info-mode))

(defun comment-or-uncomment-region-or-line ()
    "Comments or uncomments the region or the current line if there's no active region."
    (interactive)
    (let (beg end)
        (if (region-active-p)
            (setq beg (region-beginning) end (region-end))
            (setq beg (line-beginning-position) end (line-end-position)))
        (comment-or-uncomment-region beg end)))

(global-set-key (kbd "C-a") 'comment-or-uncomment-region-or-line)

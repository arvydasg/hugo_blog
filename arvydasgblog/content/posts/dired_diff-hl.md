---
title: "Dired diff-hl"
date: 2022-06-19T17:03:29+03:00
cover:
    image: direddiffhl.png
    alt: 'dired diff hl preview'
    caption: 'dired diff hl preview'
tags: ["emacs"]
categories: [""]
---

# Intro

So, everything started when I have discovered 'diff-hl' package. It
had an option to show differences in dired buffer. I thought okay,
cool option, lets not use neotree anymore and use dired instead.

# Body

I added a few lines to 'diff-hl' config to make the file changes
visible in dired buffer.

```emacs-lisp
(use-package diff-hl
  :ensure t
  :init (add-hook 'prog-mode-hook #'diff-hl-mode)
  (add-hook 'org-mode-hook #'diff-hl-mode)
  (add-hook 'dired-mode-hook 'diff-hl-dired-mode)
  (add-hook 'magit-post-refresh-hook 'diff-hl-magit-post-refresh)
  (add-hook 'magit-pre-refresh-hook 'diff-hl-magit-post-refresh))
```


I then watched some videos to remind myself of dired commands and
configs.

I saw a guy effortlessly jumping from one directory to another,
opening a file, opening a directory at point, opening another
directory, closing dired buffer with q and not complaining about many
opened buffers after he jumped between a few with dired.

First of all, I wanted the same behavior as 'neotree'. I wanted to see
the current directory and its files with one keystroke. There original
one C-x d ASKS me for a directory. C-x C-d just list a directory -
didn't understand this function. Then I discovered 'jump-to-dir' smth
like that, so I bind that to C-x C-d. Great, I can now open current
directory and see it's files quickly.

Next issues - I could navigate dired buffers with f - forward q -
backwards. BUT if I wanted to quit, I could not do it, because q was
taken already.

Then on top of that I have discovered that after navigating through a
few directories, my buffer list gets cluttered with dired buffers of
visited files. That's definitely a no-go, because I don't want to
accidentally open dired buffer that is named the same as my file when
I am looking for a file.

To fix BOTH of these issues I have discovered
'dired-find-alternate-file' command. It is bound to 'a' and it opens a
file or directory WITHOUT creating a separate buffer for it. Great!

Then it also somehow leaves 'q' unused, so I can quit dired buffer
with that keystroke. Great!

Then I rebind 'dired-find-alternate-file' to 'f', because I find it
more convenient to cycle with and I am all set!

# The final config

```emacs
 (use-package dired
    :ensure nil                         ;no need for t, because dired is built in
    :custom ((dired-listing-switches "-agho --group-directories-first"))) ;sort directories first
  (global-set-key (kbd "C-x C-d") 'dired-jump) ;open dired buffer in current location
  (define-key dired-mode-map (kbd "f") 'dired-find-alternate-file)
;; (global-set-key (kbd "C-x d") 'dired)

  ;; a function to kill dired buffers. Kind of works. Or you can use "a"
  ;; to cycle through dired and it leaves no buffers opened
  ;; DiredReuseDirectoryBuffer - https://www.emacswiki.org/emacs/DiredReuseDirectoryBuffer
  ;; KillingBuffers - https://www.emacswiki.org/emacs/KillingBuffers
  (defun kill-dired-buffers ()
    (interactive)
    (mapc (lambda (buffer)
            (when (eq 'dired-mode (buffer-local-value 'major-mode buffer))
              (kill-buffer buffer)))
          (buffer-list)))

  ;; can easily check how many buffers got opened
  (defun kill-all-dired-buffers ()
    "Kill all dired buffers."
    (interactive)
    (save-excursion
      (let ((count 0))
        (dolist (buffer (buffer-list))
          (set-buffer buffer)
          (when (equal major-mode 'dired-mode)
            (setq count (1+ count))
            (kill-buffer buffer)))
        (message "Killed %i dired buffer(s)." count))))
```

Some killing buffers commands are just extras. Was using those when I
was testing out how many opened buffers there were. But luckily I
found 'dired-find-alternate-file' :)

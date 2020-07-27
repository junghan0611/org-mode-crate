# Org Mode Crate

This repository contains my configuration for Org Mode.

I've strived to make this configuration super simple to install and
use, if you face any problems please open an issue and let me know
about it.

## Caveats

-   This configuration is ONLY known to work with Emacs 24. You are on
    your own with older versions of Emacs.

-   This configuration requires Org Mode 8.0 and above.

## Install

### Get the code:

    $ git clone https://github.com/vedang/org-mode-crate.git /path/to/org-mode-crate

### Add the following lines to your .emacs

    (add-to-list 'load-path "/path/to/org-mode-crate/")
    (setq org-directory "/path/to/org-files-dir")
    ;; Agenda does not have a key-binding by default in Emacs 24.
    ;; Provide one as a starting point.
    (global-set-key (kbd "<f12>") 'org-agenda)
    (require 'org-mode-crate)

### Press F12 to get started with your agenda

## Workflow notes

-   Create and maintain as many files in your org-directory as you want.
-   Currently, I don't handle recursively loading org files, so your
    org-directory should be a flat structure.
-   Tasks are categorized as follows:
    -   Important tasks - These tasks should be tagged with one (or more)
        of the following tags: `next`, `release`, `imp`
    -   Other tasks that should be tracked - These tasks should be tagged
        with one (or more) of the following tags: `fun`, `future`, `productive`

## Optional notes

-   You can use the convenience function \`bh/punch-in' (bound to `<f9> i`)
    to clock in a predetermined default task. All you need is the
    following one time setup:
    -   Go to the org-task you want to use as the default task.
    -   Give this task an org-id by running the function `org-id-get-create`

            M-x org-id-get-create
    -   Copy the ID (stored in the task properties) and add the following
        line above `(require 'org-mode-crate)`

            (defvar bh/organization-task-id "<task_id>")
-   Now when you start org-mode, you can press `<f9> i` to clock in the
    default task.

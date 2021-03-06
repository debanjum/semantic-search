# Emacs Khoj

*An Emacs interface for [Khoj](https://github.com/debanjum/khoj)*

## Requirements

-   Install and Run [Khoj](https://github.com/debanjum/khoj)

## Installation

-   Direct Install
    -   Put `khoj.el` in your Emacs load path. For e.g \~/.emacs.d/lisp

    -   Load via `use-package` in your \~/.emacs.d/init.el or .emacs
        file by adding below snippet

        ``` elisp
        ;; Khoj Package
        (use-package khoj
          :load-path "~/.emacs.d/lisp/khoj.el"
          :bind ("C-c s" . 'khoj))
        ```
-   With [straight.el](https://github.com/raxod502/straight.el)
    -   Add below snippet to your \~/.emacs.d/init.el or .emacs config
        file and execute it.

        ``` elisp
        ;; Khoj Package for Semantic Search
        (use-package khoj
          :after org
          :straight (khoj :type git :host github :repo "debanjum/khoj" :files (:defaults "src/interface/emacs/khoj.el"))
          :bind ("C-c s" . 'khoj))
        ```
-   With [Quelpa](https://github.com/quelpa/quelpa#installation)
    -   Ensure [Quelpa](https://github.com/quelpa/quelpa#installation),
        [quelpa-use-package](https://github.com/quelpa/quelpa-use-package#installation)
        are installed

    -   Add below snippet to your \~/.emacs.d/init.el or .emacs config
        file and execute it.

        ``` elisp
        ;; Khoj Package
        (use-package khoj
          :after org
          :quelpa (khoj :fetcher url :url "https://raw.githubusercontent.com/debanjum/khoj/master/interface/emacs/khoj.el")
          :bind ("C-c s" . 'khoj))
        ```

## Usage

1.  Open Query Interface on Client

    -   In Emacs: Call `khoj` using keybinding `C-c s` or `M-x khoj`
    -   On Web: Open <http://localhost:8000/>

2.  Query in Natural Language

    e.g \"What is the meaning of life?\" \"What are my life goals?\"

    **Note: It takes about 4s on a Mac M1 and a \>100K line corpus of
    notes**

3.  (Optional) Narrow down results further

    Include/Exclude specific words or date range from results by
    updating query with below query format

    e.g \`What is the meaning of life? -god +none dt:\"last week\"\`

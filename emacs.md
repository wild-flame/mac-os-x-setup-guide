# Emacs

## Emacs 的安装

Mac 下面的 emcas 还是有很多不同的版本的，选择使用 [GNU Emacs](<http://emacsformacosx.com/>
) 就好了。

## Emacs 的配置

Emacs 推荐使用 [spacemacs](https://github.com/syl20bnr/spacemacs) 作为基础配置。Spacemacs 整个项目还是很不错的，理念简单，一致性高，功能也不弱，项目借鉴了很多 vim 的东西，spcaemacs 巧妙的结合了二者的优点。对于一个 vimer 来说，是使用 Emacs 的不二选择。

*TIPS: 关于 spacemacs 的具体使用，可以查看相关的 [文档 (Documentation)](https://github.com/syl20bnr/spacemacs/blob/d555002308e7ce86161d3d7998e42cdcc5a9800d/doc/DOCUMENTATION.org#emacs-server)*。

### Flyspell

`Flyspell` 需要 `ispell` 才能正常使用。

```
$ brew install ispell
```

## 为 Python 打造你的 Emacs 

要点：
- Elpy
- 

TIPS:

Emacs 默认的 Python-mode 就已经包含了自动补全功能。

You can use other core Emacs functions with Python, too. For example, M-x compile/M-x recompile can be used to run tests. M-x pdb can run the Python debugger, and it integrates with Emacs' gud environment so you actually get inline breakpoints.

参考：

- 其中一个答案是 Elpy 的作者亲自写的： http://emacs.stackexchange.com/questions/9696/how-do-you-create-a-robust-python-ide-with-emacs-as-the-text-editor


---

FYI：
我自己的一些特殊配置如下。

- orgmode-mediawiki 
 
   ```
(setq dotspacemacs-additional-packages '(ox-mediawiki))
  (add-to-list 'load-path "~/.emacs.d/custom/orgmode-mediawiki")
  (require 'ox-mediawiki)
  (add-to-list 'load-path "~/.emacs.d/private/local") 
  (require 'html-fold)
  (with-eval-after-load 'smartparens
    (show-smartparens-global-mode -1))
```

- mobile-org
```
  (setq org-mobile-directory "~/Dropbox/Apps/MobileOrg")
```
- 自己用的截图函数

    ```
  (defun my-org-screenshot ()
    "Take a screenshot into a time stamped unique-named file in the
same directory as the org-buffer and insert a link to this file."
    (interactive)
    ;(org-display-inline-images)
    (setq filename
          (concat
           (make-temp-name
            (concat (file-name-nondirectory (buffer-file-name))
                    "_imgs/"
                    (format-time-string "%Y%m%d_%H%M%S_")) ) ".png"))
    (unless (file-exists-p (file-name-directory filename))
      (make-directory (file-name-directory filename)))
                                        ; take screenshot
    (if (eq system-type 'darwin)
        (call-process "screencapture" nil nil nil "-i" filename))
    (if (eq system-type 'gnu/linux)
        (call-process "import" nil nil nil filename))
                                        ; insert into file if correctly taken
    (if (file-exists-p filename)
        (insert (concat "[[./" filename "]]"))
    )
  )
    ```
- org-capture的配置

    ```
  (setq org-capture-templates '(
                                ("t" "Task" entry (file+headline "~/Dropbox/GTD/inbox.org" "Tasks")
                                 "** TODO %?\n  %i\n  %a")
                                ("b" "Book" entry (file+headline "~/Dropbox/GTD/books.org" "Books")
                                 "** TODO %?\n  %i\n  %a")
                                ("s" "Someday" entry (file+headline "~/Dropbox/GTD/somedays.org" "Somedays")
                                 "* %?\nEntered on %U\n  %i\n  %a")
                                ("w" "Work" entry (file+headline "~/Dropbox/GTD/works.org" "Works")
                                 "** TODO %?\n  %i\n  %a")
                                ("j" "Journal" entry (file+datetree "~/org/journal.org")
                                 "* %?\nEntered on %U\n  %i\n  %a")
                                ("n" "Note" entry (file+datetree "~/org/notes.org")
                                 "* %?\nEntered on %U\n  %i\n  %a")
                                ))
```
- flyspell 中键的切换
    ```  
  (eval-after-load "flyspell"
    '(progn
       (define-key flyspell-mouse-map [down-mouse-3] #'flyspell-correct-word)
       (define-key flyspell-mouse-map [mouse-3] #'undefined)
       (define-key flyspell-mouse-map [down-mouse-2] nil)
       (define-key flyspell-mouse-map [mouse-2] nil))) 
)
```
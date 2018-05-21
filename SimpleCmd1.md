#  Useful Simple Command 

## Product Name & Model Check
```
H/W info'
$ lspci; lspic -v
MainBoard (@linux)
$ dmidecode -t baseboard; dmidecode -t baseboard-product-name
```


#### VIM shortcuts
- [cheatsheet](https://www.maketecheasier.com/vim-keyboard-shortcuts-cheatsheet), [usages](http://sinoroo.tistory.com/entry/VIM-단축키-및-설정), [vim-cheat-sheet.gif](http://www.viemu.com/vi-vim-cheat-sheet.gif)

#### Jupyter Notebook
```
Converting IPython Notebook(.ipynb) to a Python file(.py)
$ jupyter nbconvert --to script [YOUR_NOTEBOOK].ipynb

Writing default config to: .jupyter/jupyter_notebook_config.py 
Running a notebook server
$ nohup jupyter notebook &
```

#### Screen 
```
$ screen -S sess_name
$ screen -list
$ screen -r sess_name
$ screen -X -S sess_name kill ($ pkill screen / $ screen -wipe)
```

#### Gitlab 
- [ubuntu-gitlab-install-use](http://html5around.com/wordpress/tutorials/ubuntu-gitlab-install-use-1/),
[Git Cheatsheet](http://kwonnam.pe.kr/wiki/git/cheatsheet), [git-usage](https://github.com/jeonghwan-kim/git-usage)
```
$ git init; git clone {url}
$ git add "file_names"
$ git commit -m "comment" 
$ git push origin master
```



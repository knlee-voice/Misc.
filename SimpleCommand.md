#  Useful Simple Command 

#### Jupyter Notebook
<pre>
Converting IPython Notebook(.ipynb) to a Python file(.py)
$ jupyter nbconvert --to script [YOUR_NOTEBOOK].ipynb

Running a notebook server
$ edit .jupyter/jupyter_notebook_config.py 
$ nohup jupyter notebook &
</pre>


#### SoX (Sound eXchange, for audio manipulation)
- [manual](http://sox.sourceforge.net/sox.html), [usages1](https://digitalcardboard.com/blog/2009/08/25/the-sox-of-silence/comment-page-2/), [usages2](http://forums.justlinux.com/showthread.php?136678-using-sox-to-trim-silence-from-the-end-of-wav-files)
```
Converting .pcm(16kHz, 16bits) to .wav
$ sox -t raw  -b 16 -e signed-integer -r 16000 -c 1 source.raw target.wav 

Capturing stats from sox
$ sox target.wav -n stat

Trimming silence at the beginning 
(trim silence - anything less than 1% volume, 0%: pure digital silence)
$ sox in.wav out.wav silence 1 0.1 1%

Trim the audio file (at 1 min 15 sec and ending at 1 min 45 sec):
$ sox in.wav out.wav trim 1:15 =1:45
$ sox in.wav out.wav trim 1:15 0:30
$ sox in.wav out.wav trim 75 30

Generate Sound effects
$ sox -n -r 16000 -c 1 synth_generate_5sec.raw synth 5 sin 347
```


#### PERL/SED/AWK 
<pre>
$ grep -v ^[[:space:]]*$ filename | wc -l
$ perl -pi -e 'tr/a-z/A-Z/' 
$ ls -1b
</pre>


#### VIM shortcuts
- [cheatsheet](https://www.maketecheasier.com/vim-keyboard-shortcuts-cheatsheet), [usages](http://sinoroo.tistory.com/entry/VIM-단축키-및-설정), [vim-cheat-sheet.gif](http://www.viemu.com/vi-vim-cheat-sheet.gif)


#### Screen 
<pre>
$ screen -S sess_name
$ screen -list
$ screen -r sess_name
$ screen -X -S sess_name kill ($ pkill screen / $ screen -wipe)
</pre>

## Product Name & Model Check
```
H/W info'
$ lspci; lspic -v
MainBoard (@linux)
$ dmidecode -t baseboard; dmidecode -t baseboard-product-name
```

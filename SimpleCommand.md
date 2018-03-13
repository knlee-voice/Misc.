#  Useful Simple Command 


Converting IPython Notebook(.ipynb) to a Python file(.py)
<pre>
$ jupyter nbconvert --to script [YOUR_NOTEBOOK].ipynb
</pre>


SoX (Sound eXchange, for audio manipulation)
- [manual](http://sox.sourceforge.net/sox.html), [usages](https://digitalcardboard.com/blog/2009/08/25/the-sox-of-silence/comment-page-2/)
```
Converting .pcm(16kHz, 16bits) to .wav
$ sox -t raw  -b 16 -e signed-integer -r 16000 -c 1 source.raw target.wav 

Capturing stats from sox
$ sox target.wav -n stat

Trimming silence at the beginning 
(trim silence - anything less than 1% volume, 0%: pure digital silence)
$ sox in.wav out1.wav silence 1 0.1 1%
```


PERL/SED/AWK 
<pre>
$ grep -v ^[[:space:]]*$ filename | wc -l
$ perl -pi -e 'tr/a-z/A-Z/' 
$ ls -1b
</pre>


VIM shortcuts
- [cheatsheet](https://www.maketecheasier.com/vim-keyboard-shortcuts-cheatsheet), [usages](http://sinoroo.tistory.com/entry/VIM-단축키-및-설정), [vim-cheat-sheet.gif](http://www.viemu.com/vi-vim-cheat-sheet.gif)

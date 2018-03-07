#  Useful Simple Command 


Converting IPython Notebook(.ipynb) to a Python file(.py)
<pre>
$ jupyter nbconvert --to script [YOUR_NOTEBOOK].ipynb
</pre>


SoX (Sound eXchange, for audio manipulation)
```
http://sox.sourceforge.net/sox.html

Converting .pcm(16kHz, 16bits) to .wav
$ sox -t raw  -b 16 -e signed-integer -r 16000 -c 1 source.raw target.wav 

Capturing stats from sox
$ sox target.wav -n stat

The Sox of Silence 
https://digitalcardboard.com/blog/2009/08/25/the-sox-of-silence/comment-page-2/
```


PERL/SED/AWK 
<pre>
$ grep -v ^[[:space:]]*$ filename | wc -l
$ perl -pi -e 'tr/a-z/A-Z/' 
$ ls -1b
</pre>

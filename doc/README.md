## Compilation

When first cloning this repo use these commands to compile the .tex/.aux files properly:

```console
$ pdflatex <file>.tex
$ bibtex <file>.aux
$ pdflatex <file>.tex
$ pdflatex <file>.tex
```

with this sequence of commands, all references wihin the document(tables/figs) and references
of other work should be working!

After this you can just run:

```console
$ pdflatex <file>.tex
```

to recompile any changes made to the .tex file.  If any changes were made to the .bib file do 
the 4 command sequence again and all is good!

___

## Bonus: Vim + Zathura live preview setup

Assuming you have zathura and vim installed, add the fillowing file to the **doc/** dir:

```bash, .vimrc
map I :! rm <filename>.pdf; pdflatex %<CR><CR>
```

The workflow i suggest is the following:

### 1. Open the .tex file in vim

Open the .tex file in vim and run the command **:so .vimrc** which will override
any previous **Shift + i** command mapped and remap it to deleting the .pdf file and 
recompiling it.

### 2. Open the pdf in zathura
```
zathura <file>.pdf
```

### 3. Press <Shift + I> inside vim

This deletes the current .pdf file, and recompiles the .tex file, and like magic you see 
any changes made to the documet **live preveiw** !



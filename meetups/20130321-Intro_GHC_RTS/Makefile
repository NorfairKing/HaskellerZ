GHC_OPTS=-O2 -ddump-prep -fforce-recomp -ddump-to-file -ddump-stg -ddump-asm -ddump-cmm -ddump-simpl -ddump-stranal -ddump-inlinings
GHC=ghc ${GHC_OPTS}

# TODO: Make slides and handout --self-contained
all: handout.html slides.html

slides.html: intro_ghc_rts-talk.md fig/*
	pandoc -f markdown+lhs -w slidy -s --self-contained intro_ghc_rts-talk.md -o slides.html

handout.html: intro_ghc_rts-talk.md fig/*
	pandoc -f markdown+lhs -s -S --toc --self-contained intro_ghc_rts-talk.md -o handout.html

clean:
	rm -f handout.html
	rm -f slides.html

enum-example:
	${GHC} Enum.hs
	
list-example:
	${GHC} List.hs

sumN-example:
	${GHC} SumN.hs

average-example:
	${GHC} Average.hs

default-example:
	${GHC} Default.hs

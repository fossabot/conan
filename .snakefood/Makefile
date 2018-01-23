NAME = conans
ROOT = ../conans
PDFS = $(NAME).pdf

.SUFFIXES: .deps .dot .pdf .clusters

all: $(PDFS)

raw.deps: $(ROOT)
	sfood -i $(ROOT) $(FOOD_FLAGS) > $@

$(NAME).clusters: $(ROOT)
	cd $(ROOT) ; find -mindepth 1 -maxdepth 1 -type d -printf '%P\n' > $(shell pwd)/$@

$(NAME).deps: $(NAME).clusters raw.deps
	cat raw.deps | sfood-cluster -f $< > $@

.deps.pdf:
	cat $< | sfood-graph | dot -Tps | ps2pdf - $@

clean:
	rm -f *.clusters *.dot *.pdf
	ls -1 *.deps | grep -v ^raw.deps | xargs rm -f

realclean: clean
	rm -f raw.deps

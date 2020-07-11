SRC := $(wildcard *solution.Rmd)
REPORTS := $(subst Rmd,md,$(SRC))
OS := $(shell uname)
# ${RSTUDIO_PASS} # Set in environment variables

all: ${REPORTS}

%solution.md: %solution.Rmd
	Rscript -e 'rmarkdown::render("$<")'

start:
	./run-rstudio

stop:
	docker stop rstudio

setup:
	docker pull rocker/geospatial
	mkdir data

unset:
	docker rm rstudio

clean:
	rm -f *assignment.Rmd *solution.Rmd

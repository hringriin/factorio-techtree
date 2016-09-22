# config
FILENAME=0.13.20
BUILDPATH=build


all: compile

vanilla:
	rm -rf ${BUILDPATH}

compile: vectorgraphics

check-build-dir:
	@if !(test -d ${BUILDPATH}/svg); \
		then mkdir -p ${BUILDPATH}/svg \
		&& echo "${BUILDPATH}/svg directory created."; \
	fi;

# zur ansicht mal alle
vectorgraphics: check-build-dir vector-dot vector-neato vector-twopi vector-circo vector-fdp vector-sfdp vector-patchwork

vector-dot:
	dot -Tsvg ${FILENAME}.dot -o ${BUILDPATH}/svg/${FILENAME}_directed.svg
	dot -Tsvgz ${FILENAME}.dot -o ${BUILDPATH}/svg/${FILENAME}_directed.svgz

vector-neato:
	neato -Tsvg ${FILENAME}.dot -o ${BUILDPATH}/svg/${FILENAME}_undirected.svg
	neato -Tsvgz ${FILENAME}.dot -o ${BUILDPATH}/svg/${FILENAME}_undirected.svgz

vector-twopi:
	twopi -Tsvg ${FILENAME}.dot -o ${BUILDPATH}/svg/${FILENAME}_radial.svg
	twopi -Tsvgz ${FILENAME}.dot -o ${BUILDPATH}/svg/${FILENAME}_radial.svgz

vector-circo:
	circo -Tsvg ${FILENAME}.dot -o ${BUILDPATH}/svg/${FILENAME}_circular.svg
	circo -Tsvgz ${FILENAME}.dot -o ${BUILDPATH}/svg/${FILENAME}_circular.svgz

vector-fdp:
	fdp -Tsvg ${FILENAME}.dot -o ${BUILDPATH}/svg/${FILENAME}_undirected2.svg
	fdp -Tsvgz ${FILENAME}.dot -o ${BUILDPATH}/svg/${FILENAME}_undirected2.svgz

vector-sfdp:
	sfdp -Tsvg ${FILENAME}.dot -o ${BUILDPATH}/svg/${FILENAME}_large-undirected2.svg
	sfdp -Tsvgz ${FILENAME}.dot -o ${BUILDPATH}/svg/${FILENAME}_large-undirected2.svgz

vector-patchwork:
	patchwork -Tsvg ${FILENAME}.dot -o ${BUILDPATH}/svg/${FILENAME}_treemap.svg
	patchwork -Tsvgz ${FILENAME}.dot -o ${BUILDPATH}/svg/${FILENAME}_treemap.svgz

# Moeglicher Weise spannend, aber Benutzung unklar
imagemap:
	@if !(test -d ${BUILDPATH}/imagemap); \
		then mkdir -p ${BUILDPATH}/imagemap \
		&& echo "${BUILDPATH}/imagemap directory created."; \
	fi;
	dot -Timap ${FILENAME}.dot -o ${FILENAME}.imap

# Moeglicher Weise spannend, aber Benutzung unklar
client-side-imagemap:
	@if !(test -d ${BUILDPATH}/client-side-imagemap); \
		then mkdir -p ${BUILDPATH}/client-side-imagemap \
		&& echo "${BUILDPATH}/client-side-imagemap directory created."; \
	fi;
	dot -Tcmapx ${FILENAME}.dot -o ${FILENAME}.cmapx

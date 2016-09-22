# config
FILENAME=example
BUILDPATH=build


all: compile

compile: vectorgraphics imagemap

# Erstmal ausreichend
vectorgraphics:
	@if !(test -d ${BUILDPATH}/svg); \
		then mkdir -p ${BUILDPATH}/svg \
		&& echo "${BUILDPATH}/svg directory created."; \
	fi;
	dot -Tsvg ${FILENAME}.dot -o ${BUILDPATH}/svg/${FILENAME}.svg
	dot -Tsvgz ${FILENAME}.dot -o ${BUILDPATH}/svg/${FILENAME}.svgz

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

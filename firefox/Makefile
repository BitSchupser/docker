NAME := firefox
CONTAINER := bitschupser/$(NAME)
DATA := ~/.docker/data/$(NAME)
TARBALL := firefox-docker-0.1.0.tar.bz2

build: Dockerfile
	docker build -t $(CONTAINER) .

run: build
	./docker-firefox.sh $(CONTAINER) $(DATA)

tar: Dockerfile firefox-docker Makefile PKGBUILD
	tar cjf ${TARBALL} $?
	sed -i -e '/^md5sum/d' -e "s/^source.*$$/&\n$$(makepkg -g)/" PKGBUILD

install: build
	mkdir -p ${DESTDIR}/usr/bin/
	install -m 755 firefox-docker ${DESTDIR}/usr/bin/

clean:
	rm -rf ${TARBALL} src pkg *.pkg.tar.xz

PYTHONLIBDIR ?= $(shell  python2 -c "from distutils.sysconfig import *; print get_python_lib()")
PACKAGEDIR ?= $(DESTDIR)/$(PYTHONLIBDIR)/ipa
CONFIGDIR ?= $(DESTDIR)/etc/ipa
PYTHONS ?= python2 python3

all:
	python2 setup.py build

install:
	@for python in $(PYTHONS); do \
		if [ "$(DESTDIR)" = "" ]; then \
			$$python setup.py install; \
		else \
			$$python setup.py install --root $(DESTDIR); \
		fi \
	done

clean:
	rm -rf build

distclean: clean

maintainer-clean: distclean

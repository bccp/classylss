DEST?=_inst

TARBALL=class-v$(CLASS_VERSION).tar.gz
UNPACK=tmp-class-v$(CLASS_VERSION)
SRC=$(UNPACK)/class_public-$(CLASS_VERSION)

$(TARBALL):
	curl -fsSL https://github.com/lesgourg/class_public/archive/v$(CLASS_VERSION).tar.gz \
		> $(TARBALL)

$(SRC)/stamp.unzip: $(TARBALL)
	mkdir -p $(UNPACK)
	gzip -dc $(TARBALL) | tar xf - -C $(UNPACK)
	touch $@

$(SRC)/libclass.a: $(SRC)/stamp.unzip Makefile
	cd $(SRC); make libclass.a CLASSDIR=$(CLASSDIR)

$(DEST)/lib/libclass.a: $(SRC)/libclass.a Makefile
	echo $(DEST)/data
	mkdir -p $(DEST)/data
	cp -r $(SRC)/include $(DEST)
	mkdir -p $(DEST)/lib
	cp $(SRC)/libclass.a $(DEST)/lib
	mkdir -p $(DEST)/data
	./copy_data_files $(SRC) $(DEST)/data
	cp $(SRC)/external/*/*.h $(DEST)/include


unzip: $(SRC)/stamp.unzip
build: $(SRC)/libclass.a
install: $(DEST)/lib/libclass.a

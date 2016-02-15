echo "auto makefile ..."

cat << END > Makefile
default:
	export GOPATH=$LCAT_ROOT; go install lcat

clean:
	rm -rf $LCAT_ROOT/bin
	rm -rf $LCAT_ROOT/src/github.com/
	rm -rf $LCAT_ROOT/pkg/
	rm -f Makefile

install : $LCAT_ROOT/bin/aim-mapd
	test -d '\$(DESTDIR)$LCAT_PREFIX' || mkdir -p '\$(DESTDIR)$LCAT_PREFIX'
	test -d '\$(DESTDIR)$LCAT_BIN_DIR' || mkdir -p '\$(DESTDIR)$LCAT_BIN_DIR'
	test -d '\$(DESTDIR)$LCAT_LOG_DIR' || mkdir -p '\$(DESTDIR)$LCAT_LOG_DIR'
	test -d '\$(DESTDIR)$LCAT_CONF_DIR' || mkdir -p '\$(DESTDIR)$LCAT_CONF_DIR'
	cp $LCAT_ROOT/bin/* \$(DESTDIR)/$LCAT_BIN_DIR/ -rf
	test -f '\$(DESTDIR)$LCAT_CONF_DIR/lcat.conf' || cp $LCAT_ROOT/conf/lcat.conf '\$(DESTDIR)/$LCAT_CONF_DIR/lcat.conf'
END

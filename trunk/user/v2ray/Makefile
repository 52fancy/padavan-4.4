THISDIR := $(shell pwd)
V2RAY_URL_BASE := https://github.com/v2fly/v2ray-core/releases/latest/download

V2RAY_NAME := v2ray-linux-mips32le
V2RAY_URL := $(V2RAY_URL_BASE)/$(V2RAY_NAME).zip

all: extra_test
	@echo "v2ray build done!"

download_test:
	( if [ ! -f $(V2RAY_NAME).zip ]; then \
		wget -t5 --timeout=20 --no-check-certificate -O $(V2RAY_NAME).zip $(V2RAY_URL); \
	fi )

extra_test:
	( tar -zxf v2ray.tar.gz )

clean:
	rm -rf $(V2RAY_NAME).zip

romfs:
	$(ROMFSINST) -p +x $(THISDIR)/v2ray /usr/v2ray
	$(ROMFSINST) -p +x $(THISDIR)/geosite.dat /usr/geosite.dat

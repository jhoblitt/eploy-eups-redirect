UNAME := $(shell uname -s | tr A-Z a-z)
BIN_DIR=./bin
TF_VERSION=0.9.11
ZIP_FILE=terraform_$(TF_VERSION)_$(UNAME)_amd64.zip

$(BIN_DIR):
	mkdir $@
	cd $@; wget -nc https://releases.hashicorp.com/terraform/$(TF_VERSION)/$(ZIP_FILE)
	cd $@; unzip $(ZIP_FILE)

tf := $(wildcard *.tf)

fmt:
	$(foreach src, $(tf), $(BIN_DIR)/terraform fmt $(src);)

clean:
	-rm -rf bin

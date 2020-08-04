CFCM=node_modules/.bin/commonform-commonmark
CFDOCX=node_modules/.bin/commonform-docx
CRITIQUE=node_modules/.bin/commonform-critique
JSON=node_modules/.bin/json
LINT=node_modules/.bin/commonform-lint
MUSTACHE=node_modules/.bin/mustache
TOOLS=$(CFCM) $(CFDOCX) $(CRITIQUE) $(JSON) $(LINT) $(MUSTACHE)

BUILD=build
GITHUB_MARKDOWN=README.md CONTRIBUTING.md
BASENAMES=$(basename $(filter-out $(GITHUB_MARKDOWN),$(wildcard *.md)))
FORMS=$(addsuffix .form.json,$(addprefix $(BUILD)/,$(BASENAMES)))

GIT_TAG=$(shell (git diff-index --quiet HEAD && git describe --exact-match --tags 2>/dev/null | sed 's/v//'))

all: docx pdf md

docx: $(addprefix $(BUILD)/,$(BASENAMES:=.docx))
pdf: $(addprefix $(BUILD)/,$(BASENAMES:=.pdf))
md: $(addprefix $(BUILD)/,$(BASENAMES:=.md))

$(BUILD)/%.docx: $(BUILD)/%.form.json $(BUILD)/%.title $(BUILD)/%.edition $(BUILD)/%.signatures styles.json | $(CFDOCX) $(BUILD)
	$(CFDOCX) --title "$(shell cat $(BUILD)/$*.title)" --edition "$(shell cat $(BUILD)/$*.edition)" --signatures $(BUILD)/$*.signatures --number outline --indent-margins --left-align-title --styles styles.json $< > $@

$(BUILD)/%.md: $(BUILD)/%.form.json $(BUILD)/%.title $(BUILD)/%.edition $(BUILD)/%.signatures | $(CFCM) $(BUILD)
	$(CFCM) stringify --title "$(shell cat $(BUILD)/$*.title)" --edition "$(shell cat $(BUILD)/$*.edition)" --signatures $(BUILD)/$*.signatures --ordered --ids < $< > $@

$(BUILD)/%.parsed: %.md | $(BUILD) $(CFCM)
	$(CFCM) parse < $< > $@

$(BUILD)/%.form.json: $(BUILD)/%.parsed | $(JSON)
	$(JSON) form < $< > $@

$(BUILD)/%.title: $(BUILD)/%.parsed | $(JSON)
	json frontMatter.title < $< > $@

$(BUILD)/%.edition: $(BUILD)/%.parsed | $(JSON)
	json frontMatter.edition < $< > $@

$(BUILD)/%.signatures: $(BUILD)/%.parsed | $(JSON)
	json frontMatter.signatures < $< > $@

$(BUILD)/%.directions: $(BUILD)/%.parsed | $(JSON)
	json directions < $< > $@

%.pdf: %.docx
	unoconv $<

$(BUILD):
	mkdir -p $@

$(TOOLS):
	npm ci

.PHONY: clean docker lint critique

lint: $(FORMS) | $(LINT) $(JSON)
	@for form in $(FORMS); do \
		echo ; \
		echo $$form; \
		cat $$form | $(LINT) | $(JSON) -a message | sort -u; \
	done; \

critique: $(FORMS) | $(CRITIQUE) $(JSON)
	@for form in $(FORMS); do \
		echo ; \
		echo $$form ; \
		cat $$form | $(CRITIQUE) | $(JSON) -a message | sort -u; \
	done

clean:
	rm -rf $(BUILD)

docker:
	docker build -t blockchain-commons-security-services-terms .
	docker run --name blockchain-commons-security-services-terms blockchain-commons-security-services-terms
	docker cp blockchain-commons-security-services-terms:/workdir/$(BUILD) .
	docker rm blockchain-commons-security-services-terms

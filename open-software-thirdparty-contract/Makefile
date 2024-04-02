CFCM=node_modules/.bin/commonform-commonmark
CFDOCX=node_modules/.bin/commonform-docx
CRITIQUE=node_modules/.bin/commonform-critique
JSON=node_modules/.bin/json
LINT=node_modules/.bin/commonform-lint
MUSTACHE=node_modules/.bin/mustache
TOOLS=$(CFCM) $(CFDOCX) $(CRITIQUE) $(JSON) $(LINT) $(MUSTACHE)

BUILD=build
DOCKER_TAG=blockchain-commons-open-development
GITHUB_MARKDOWN=README.md CONTRIBUTING.md
BASENAMES=$(basename $(filter-out $(GITHUB_MARKDOWN),$(wildcard *.md)))
FORMS=$(addsuffix .form.json,$(addprefix $(BUILD)/,$(BASENAMES)))

all: docx pdf md

docx: $(addprefix $(BUILD)/,$(BASENAMES:=.docx))
pdf: $(addprefix $(BUILD)/,$(BASENAMES:=.pdf))
md: $(addprefix $(BUILD)/,$(BASENAMES:=.md))

$(BUILD)/%.docx: $(BUILD)/%.form $(BUILD)/%.title $(BUILD)/%.edition $(BUILD)/%.signatures $(BUILD)/%.directions $(BUILD)/%.values styles.json | $(CFDOCX) $(BUILD)
	$(CFDOCX) \
		--directions $(BUILD)/$*.directions \
		--edition "$(shell cat $(BUILD)/$*.edition)" \
		--indent-margins \
		--left-align-title \
		--number outline \
		--signatures $(BUILD)/$*.signatures \
		--styles styles.json \
		--title "$(shell cat $(BUILD)/$*.title)" \
		--values $(BUILD)/$*.values \
		$< > $@

$(BUILD)/%.md: $(BUILD)/%.form $(BUILD)/%.title $(BUILD)/%.edition $(BUILD)/%.signatures $(BUILD)/%.directions $(BUILD)/%.values | $(CFCM) $(BUILD)
	$(CFCM) stringify \
		--directions $(BUILD)/$*.directions \
		--edition "$(shell cat $(BUILD)/$*.edition)" \
		--ids \
		--ordered \
		--title "$(shell cat $(BUILD)/$*.title)" \
		--values $(BUILD)/$*.values \
		< $< > $@

$(BUILD)/%.parsed: %.md | $(BUILD) $(CFCM)
	$(CFCM) parse < $< > $@

$(BUILD)/%.form: $(BUILD)/%.parsed | $(JSON)
	$(JSON) form < $< > $@

$(BUILD)/%.title: $(BUILD)/%.parsed | $(JSON)
	json frontMatter.title < $< > $@

$(BUILD)/%.edition: $(BUILD)/%.parsed | $(JSON)
	json frontMatter.edition < $< > $@

$(BUILD)/%.signatures: $(BUILD)/%.parsed | $(JSON)
	json frontMatter.signatures < $< > $@

$(BUILD)/%.directions: $(BUILD)/%.parsed | $(JSON)
	json directions < $< > $@

$(BUILD)/%.values: $(BUILD)/%.parsed | $(JSON)
	json frontMatter.blanks < $< > $@

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
	docker build -t $(DOCKER_TAG) .
	docker run --name $(DOCKER_TAG) $(DOCKER_TAG)
	docker cp $(DOCKER_TAG):/workdir/$(BUILD) .
	docker rm $(DOCKER_TAG)

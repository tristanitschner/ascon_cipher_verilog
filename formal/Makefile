SBY_FILES := $(wildcard *.sby)

COVER_TARGETS := $(SBY_FILES:.sby=_cover)
BMC_TARGETS   := $(SBY_FILES:.sby=_bmc)

all: cover bmc

.PHONY: cover bmc

cover: $(COVER_TARGETS)
bmc:   $(BMC_TARGETS)

%_cover: %.sby
	sby -f $< cover
	touch $@

%_bmc: %.sby
	sby -f $< bmc
	touch $@

clean:
	$(RM) $(COVER_TARGETS)
	$(RM) $(BMC_TARGETS

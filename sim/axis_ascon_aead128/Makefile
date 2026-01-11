SRC += axis_ascon_aead128_tb.v

SRC += ../../rtl/ascon_aead128_core.v
SRC += ../../rtl/ascon_aead128.v
SRC += ../../rtl/ascon_isolator.v
SRC += ../../rtl/ascon_pad.v
SRC += ../../rtl/ascon_p.v
SRC += ../../rtl/ascon_regslice.v
SRC += ../../rtl/ascon_round.v
SRC += ../../rtl/ascon_skidbuffer.v
SRC += ../../rtl/axis_ascon_aead128.v

# TODO: move this file somewhere more general
SRC += ../../formal_rtl/formal_fifo.v

IFLAGS += -g2005-sv

VFLAGS += -fst

all: ascon_aead128_tb.ran

%.ran: %.iv
	vvp $< $(VFLAGS)
	touch $@

ascon_aead128_tb.iv: $(SRC)
	iverilog $(IFLAGS) $(SRC) -o $@

.PHONY: clean
clean:
	$(RM) *.vcd
	$(RM) *.iv
	$(RM) *.ran


LIBRARYPATHS = "_libraries"
ASMFILE = "out.bba"
MACHINEFILE = "out.bbx"
PROFILECOMPILER = --profile
VIEWEXECUTION = --view-short
EMITINTERMEDIATE = #--emit-offsets --emit-tac --emit-pil
EMITINDICES = #--emit-indices
MAXINSTRUCTIONS = 10000000

all:
	@clear
	@echo "Compiling (pmax -> assembly)"
	@pmax build --target-name $(ASMFILE) --lib-paths $(LIBRARYPATHS) $(PROFILECOMPILER) $(EMITINTERMEDIATE)
	@echo "Assembling (assembly -> binary)"
	@bbasm assemble _targets/$(ASMFILE) _targets/$(MACHINEFILE) $(EMITINDICES) --print-stats
	@echo "Running (binary)"
	@bbvm run _targets/$(MACHINEFILE) $(VIEWEXECUTION) --max-instructions $(MAXINSTRUCTIONS)

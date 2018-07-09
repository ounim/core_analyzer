
PLATFORM = Linux_x86_64
COMPILER = g++
LINKER   = $(COMPILER)

PLATFORM_OBJ = core_elf.o core_elf_linux_x86_64.o heap_ptmalloc.o

COMP_OPT = -g -O -fpermissive -c -m64 -I$(INC)

EXEC_LDFLAGS = -g -O -m64 -Wl,--no-undefined

SRC = .
INC = $(SRC)

INC_FILES = $(SRC)/cmd_impl.h

all: core_analyzer

core_analyzer: main.o util.o search.o segment.o stl_container.o heap.o $(PLATFORM_OBJ)
	$(LINKER) $(EXEC_LDFLAGS) -o $@ $^

%.o: $(SRC)/%.cpp $(INC_FILES)
	$(COMPILER) $(COMP_OPT) -DNDEBUG $(MSTR_INC) $<

clean:
	rm *.o core_analyzer

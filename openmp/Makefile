OPT	 := -O3 -fopenmp
CC       := clang
CFLAGS   := $(OPT) -std=c11
FC	 := ifort
FFLAGS   := $(OPT)
LD       := $(CC)
LDFLAGS  := $(OPT)
LIBS     :=

TESTS = redcrit matrix fusion nesting tls gems gems2 flush # distribute

all: $(TESTS)

%: %.o
	$(LD) $(LDFLAGS) $< $(LIBS) -o $@

%: %.c
	$(CC) $(CFLAGS) $< -o $@

%: %.f90
	$(FC) $(FFLAGS) $< -o $@

clean:
	-rm -f *.o
	-rm -f $(TESTS)


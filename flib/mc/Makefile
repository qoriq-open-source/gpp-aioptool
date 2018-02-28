PWD:= .

CC=$(CROSS_COMPILE)gcc
LD=${CROSS_COMPILE}ld
AR=${CROSS_COMPILE}ar


TARGET=	libmcflib.a

CFLAGS = -I$(PWD) -W -Wall -Wshadow -Wstrict-prototypes
CFLAGS += -I$(SDKTARGETSYSROOT)/usr/include

SOURCES=dpaiop.c \
	mc_sys.c

OBJECTS=$(SOURCES:.c=.o)

all:     $(TARGET)
	 @echo $(TARGET) has been created

$(TARGET):$(OBJECTS)
	 @echo "Creating" $@
	 $(AR) ruv $@ $(OBJECTS)
	 ranlib $@

.c.o:
	 @echo "Compiling" $*.c
	 $(CC) $(CFLAGS) -c $< -o $@

clean:
	@echo "Cleaning up..."
	rm -f *.o *.a

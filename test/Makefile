all: basicwrite basicread

clean:
	rm -f basicwrite basicread *.o *.lst 

INCDIR=../include

basicread: basicread.o ../src/*.o
	$(LD) $(LDFLAGS) -o $@ $< ../src/*.o $(LIBS)

basicwrite: basicwrite.o ../src/*.o
	$(LD) $(LDFLAGS) -o $@ $< ../src/*.o $(LIBS)

basicread.o: basicread.c $(INCDIR)/*.h
	$(CC) -qascii $(CFLAGS) $(CPPFLAGS) -I$(INCDIR) -c $<

basicwrite.o: basicwrite.c $(INCDIR)/*.h
	$(CC) -qascii $(CFLAGS) $(CPPFLAGS) -I$(INCDIR) -c $<

check: basicread basicwrite
	./testwritethenread.sh

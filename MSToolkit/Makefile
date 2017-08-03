#Set your paths here.
ZLIB_PATH = ./src/zlib-1.2.8
MZPARSER_PATH = ./src/mzParser
EXPAT_PATH = ./src/expat-2.0.1
SQLITE_PATH = ./src/sqlite-3.7.7.1
MST_PATH = ./src/MSToolkit

HEADER_PATH = ./include

MZPARSER = mzp.MSNumpress.o mzp.mzp_base64.o mzp.BasicSpectrum.o mzp.mzParser.o mzp.RAMPface.o mzp.saxhandler.o mzp.saxmzmlhandler.o \
	mzp.saxmzxmlhandler.o mzp.Czran.o mzp.mz5handler.o mzp.mzpMz5Config.o mzp.mzpMz5Structs.o mzp.BasicChromatogram.o mzp.PWIZface.o
MZPARSER_DEBUG = mzp.MSNumpress.o mzp.mzp_base64.o mzp.BasicSpectrum.o mzp.mzParser.o mzp.RAMPface_debug.o mzp.saxhandler_debug.o mzp.saxmzmlhandler.o \
	mzp.saxmzxmlhandler_debug.o mzp.Czran.o mzp.mz5handler.o mzp.mzpMz5Config.o mzp.mzpMz5Structs.o mzp.BasicChromatogram.o mzp.PWIZface.o
MZPARSERLITE = mzp.MSNumpress.o mzp.mzp_base64_lite.o mzp.BasicSpectrum_lite.o mzp.mzParser_lite.o mzp.RAMPface_lite.o mzp.saxhandler_lite.o mzp.saxmzmlhandler_lite.o \
  mzp.saxmzxmlhandler_lite.o mzp.Czran_lite.o mzp.mz5handler_lite.o mzp.mzpMz5Config_lite.o mzp.mzpMz5Structs_lite.o mzp.BasicChromatogram_lite.o mzp.PWIZface_lite.o
MZPARSERLITE_DEBUG = mzp.MSNumpress.o mzp.mzp_base64_lite.o mzp.BasicSpectrum_lite.o mzp.mzParser_lite_debug.o mzp.RAMPface_lite.o mzp.saxhandler_lite_debug.o mzp.saxmzmlhandler_lite.o \
  mzp.saxmzxmlhandler_lite_debug.o mzp.Czran_lite.o mzp.mz5handler_lite.o mzp.mzpMz5Config_lite.o mzp.mzpMz5Structs_lite.o mzp.BasicChromatogram_lite.o mzp.PWIZface_lite.o
EXPAT = xmlparse.o xmlrole.o xmltok.o
ZLIB = adler32.o compress.o crc32.o deflate.o inffast.o inflate.o infback.o inftrees.o trees.o uncompr.o zutil.o
MSTOOLKIT = Spectrum.o MSObject.o mzMLWriter.o
READER = MSReader.o
READER_DEBUG = MSReader_debug.o
READERLITE = MSReaderLite.o
READERLITE_DEBUG = MSReaderLite_debug.o
#SQLITE = sqlite3.o 

CC = g++
GCC = gcc
NOSQLITE = -D_NOSQLITE

CFLAGS = -O3 -static -I. -I$(HEADER_PATH) -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -DGCC -DHAVE_EXPAT_CONFIG_H
CFLAGS_DEBUG = -g -static -I. -I$(HEADER_PATH) -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -DGCC -DHAVE_EXPAT_CONFIG_H
LIBS = -lm -lpthread -ldl

all:  $(ZLIB) $(MZPARSER) $(MZPARSERLITE) $(MSTOOLKIT) $(READER) $(READERLITE) $(EXPAT) $(SQLITE)
	ar rcs libmstoolkitlite.a $(ZLIB) $(EXPAT) $(MZPARSERLITE) $(MSTOOLKIT) $(READERLITE)
	ar rcs libmstoolkit.a $(ZLIB) $(EXPAT) $(MZPARSER) $(MSTOOLKIT) $(READER) $(SQLITE)
#	$(CC) $(CFLAGS) MSTDemo.cpp -L. -lmstoolkitlite -o MSTDemo
#	$(CC) $(CFLAGS) -I./include MSSingleScan/MSSingleScan.cpp -L. -lmstoolkitlite -o msSingleScan
#	$(CC) $(CFLAGS) MSConvertFile.cpp -L. -lmstoolkitlite -o MSConvertFile

lite: $(ZLIB) $(MZPARSERLITE) $(MSTOOLKIT) $(READERLITE) $(EXPAT)
	ar rcs libmstoolkitlite.a $(ZLIB) $(EXPAT) $(MZPARSERLITE) $(MSTOOLKIT) $(READERLITE)
#	$(CC) $(CFLAGS) -I./include MSSingleScan/MSSingleScan.cpp -L. -lmstoolkitlite -o msSingleScan

clean:
	rm -f *.o libmstoolkitlite.a libmstoolkit.a libmstoolkitlite_debug.a libmstoolkit_debug.a msSingleScan

#debug:  $(ZLIB) $(MZPARSER_DEBUG) $(MZPARSERLITE_DEBUG) $(MSTOOLKIT) $(READER_DEBUG) $(READERLITE) $(EXPAT) #$(SQLITE)
#	ar rcs libmstoolkitlite_debug.a $(ZLIB) $(EXPAT) $(MSTOOLKIT) $(READERLITE)
#	ar rcs libmstoolkit_debug.a $(ZLIB) $(EXPAT) $(MZPARSER_DEBUG) $(MSTOOLKIT) $(READER_DEBUG) #$(NOSQLITE)
debug:  $(ZLIB) $(MZPARSER_DEBUG) $(MZPARSERLITE_DEBUG) $(MSTOOLKIT) $(READER_DEBUG) $(READERLITE_DEBUG) $(EXPAT) #$(SQLITE)
	ar rcs libmstoolkitlite_debug.a $(ZLIB) $(EXPAT) $(MZPARSERLITE_DEBUG) $(MSTOOLKIT) $(READERLITE_DEBUG)
#	ar rcs libmstoolkit_debug.a $(ZLIB) $(EXPAT) $(MZPARSER) $(MSTOOLKIT) $(READER_DEBUG) #$(NOSQLITE)
	ar rcs libmstoolkit.a $(ZLIB) $(EXPAT) $(MZPARSER_DEBUG) $(MSTOOLKIT) $(READER_DEBUG) #$(NOSQLITE)

# zLib objects

adler32.o : $(ZLIB_PATH)/adler32.c
	$(GCC) $(CFLAGS) $(ZLIB_PATH)/adler32.c -c

compress.o : $(ZLIB_PATH)/compress.c
	$(GCC) $(CFLAGS) $(ZLIB_PATH)/compress.c -c

crc32.o : $(ZLIB_PATH)/crc32.c
	$(GCC) $(CFLAGS) $(ZLIB_PATH)/crc32.c -c

deflate.o : $(ZLIB_PATH)/deflate.c
	$(GCC) $(CFLAGS) $(ZLIB_PATH)/deflate.c -c

inffast.o : $(ZLIB_PATH)/inffast.c
	$(GCC) $(CFLAGS) $(ZLIB_PATH)/inffast.c -c

inflate.o : $(ZLIB_PATH)/inflate.c
	$(GCC) $(CFLAGS) $(ZLIB_PATH)/inflate.c -c

infback.o : $(ZLIB_PATH)/infback.c
	$(GCC) $(CFLAGS) $(ZLIB_PATH)/infback.c -c

inftrees.o : $(ZLIB_PATH)/inftrees.c
	$(GCC) $(CFLAGS) $(ZLIB_PATH)/inftrees.c -c

trees.o : $(ZLIB_PATH)/trees.c
	$(GCC) $(CFLAGS) $(ZLIB_PATH)/trees.c -c

uncompr.o : $(ZLIB_PATH)/uncompr.c
	$(GCC) $(CFLAGS) $(ZLIB_PATH)/uncompr.c -c

zutil.o : $(ZLIB_PATH)/zutil.c
	$(GCC) $(CFLAGS) $(ZLIB_PATH)/zutil.c -c



#mzParser objects
mzp.%.o : $(MZPARSER_PATH)/%.cpp
	$(CC) $(CFLAGS) $(MZ5) $< -c -o $@

#mzParser_debug objects
mzp.%_debug.o : $(MZPARSER_PATH)/%.cpp
	$(CC) $(CFLAGS_DEBUG) $(MZ5) $< -c -o $@

#mzParserLite objects
mzp.%_lite.o : $(MZPARSER_PATH)/%.cpp
	$(CC) $(CFLAGS) $< -c -o $@

#mzParserLite_debug objects
mzp.%_lite_debug.o : $(MZPARSER_PATH)/%.cpp
	$(CC) $(CFLAGS_DEBUG) $< -c -o $@


#expat objects
xmlparse.o : $(EXPAT_PATH)/xmlparse.c
	$(GCC) $(CFLAGS) $(EXPAT_PATH)/xmlparse.c -c
xmlrole.o : $(EXPAT_PATH)/xmlrole.c
	$(GCC) $(CFLAGS) $(EXPAT_PATH)/xmlrole.c -c
xmltok.o : $(EXPAT_PATH)/xmltok.c
	$(GCC) $(CFLAGS) $(EXPAT_PATH)/xmltok.c -c



#SQLite object
sqlite3.o : $(SQLITE_PATH)/sqlite3.c
	$(GCC) $(CFLAGS) $(SQLITE_PATH)/sqlite3.c -c




#MSToolkit objects

Spectrum.o : $(MST_PATH)/Spectrum.cpp
	$(CC) $(CFLAGS) $(MST_PATH)/Spectrum.cpp -c

MSReader.o : $(MST_PATH)/MSReader.cpp
	$(CC) $(CFLAGS) $(MZ5) $(MST_PATH)/MSReader.cpp -c

MSReader_debug.o : $(MST_PATH)/MSReader.cpp
	$(CC) $(CFLAGS_DEBUG) $(MZ5) $(MST_PATH)/MSReader.cpp -c -o MSReader_debug.o

MSReaderLite.o : $(MST_PATH)/MSReader.cpp
	$(CC) $(CFLAGS) $(NOSQLITE) $(MST_PATH)/MSReader.cpp -c -o MSReaderLite.o

MSReaderLite_debug.o : $(MST_PATH)/MSReader.cpp
	$(CC) $(CFLAGS_DEBUG) $(NOSQLITE) $(MST_PATH)/MSReader.cpp -c -o MSReaderLite_debug.o

MSObject.o : $(MST_PATH)/MSObject.cpp
	$(CC) $(CFLAGS) $(MST_PATH)/MSObject.cpp -c

mzMLWriter.o : $(MST_PATH)/mzMLWriter.cpp
	$(CC) $(CFLAGS) $(MST_PATH)/mzMLWriter.cpp -c





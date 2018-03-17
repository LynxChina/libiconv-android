# libiconv-android

copy the last stage version from http://www.gnu.org/software/libiconv/ into src/main/jni.

cd ./libiconv
./configure


find file config.h, change

 #define HAVE_LANGINFO_CODESET 1

to

 #define HAVE_LANGINFO_CODESET 0
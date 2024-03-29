<h1>GCC Cross Compiler Build Script</h1>

This is a simple bash script that builds a cross compiler using base GCC packages. It was made on Arch Linux, however, it should also work on other distributions, provided the script is properly translated. To build the cross compiler, first make sure you have a stable internet connection, then simply download the script, and execute it. 

<h2>Build Process</h2>

Before executing the script you may want to read the following for some additional information:

Lines 5 and 6 set the values of two variables needed throughout the process. <code>$PREFIX</code> is the directory where you want to build the compiler, and <code>$TARGET</code> is the target platform for which the cross compiler will be able to compile code. Both of these can be changed freely depending on your preferences.

Line 9 TEMPORARILY adds the directory that will contain the compiler binaries to the <code>PATH</code> environment variable for the duration of the current terminal session. To add it permanently, you will need to modify the .bashrc file located in <code>/$HOME</code> directory by adding the following line:

<code>export PATH="build-directory/bin:$PATH"</code>\
NOTE: Replace build-directory with the directory where your cross compiler will be located (<code>$PREFIX</code>)

Lines 12 to 35 download and extract all required packages, and then build the cross compiler. Know that other than <code>$PREFIX</code>, all created or downloaded files and directories are only needed during the build process and can freely be removed after. After the process is complete you can find them all in <code>/tmp/src</code>.

The script downloads and extracts two packages:
* binutils-2.41; Official repository: https://ftp.gnu.org/gnu/binutils
* gcc-13.2.0; Official repository: https://ftp.gnu.org/gnu/gcc

Package names are defined under <code>$binutils</code> and <code>$gcc</code>. If you wish to use different versions, simply change the version numbers in the two variables. To see all package releases, click on the above links, to view the official repositories. 

For more information about what's happening in the script and cross compilers in general, see the following page:\
https://wiki.osdev.org/GCC_Cross-Compiler

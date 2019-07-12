# crunchersharp
Program analyses debugger information file (PDB, so Microsoft Visual C++ only) and presents info about user defined structures (size, padding, etc). 

Original blog post: http://msinilo.pl/blog/?p=425
# Getting Started

Note that you will need the `msdia` classes to be registered. To do this:
### Windows 10 Visual Studio 2017

1. Clone the repo
   ```
   git clone https://github.com/BenHoffmanEpic/crunchersharp.git
   ```
2. Open command prompt as admin 
3. Find the directory where your `msdia` dll is located, normal it is in the follow location: 

  ```
  cd C:\Program Files (x86)\Microsoft Visual Studio\2017\Professional\Common7\IDE
  ```
  
 * Note that thise location may differ for different version of Visual Studio. I am doing this with 
   VS 2017 Version 15.9.11
4. Register the `msdia` dll manually: 
```
regsvr32 msdia140.dll
```
 * There may be more than one `msdia` DLL's in this directory, so you have to specify the version that you will 

### Other version of Visual Studio

  1) Find the msdia DLL corresponding to the version of the compiler you used to build the application. 
      -- If you have Visual Studio installed, this DLL can be found in "C:\Program Files (x86)\Microsoft Visual Studio <VERSION>\Common7\IDE", where <VERSION> corresponds to your compiler version (e.g. "12.0" for Microsoft Visual Studi 2013)
      -- If you don't have the compiler installed, download the appropriate "Microsoft Visual C++ <VERSION> Redistributable Package" and install it. 
  
  2) Open an elevated (admin) command prompt in the directory containing msdia<VERSION>.dll. 

  3) Manually register the DLL by typing "regsvr32 msdia<VERSION>.dll" (e.g. "regsvr32 msdia12.dll" for Visual Studio 2013)

![Screenshot](http://msinilo.pl/blog2/images/Crunchingbytes_118E2/cruncher.jpg "Example screenshot")

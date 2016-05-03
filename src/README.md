# Procedure for obtaining and building the foam-extend 3.2 source code

1. Download the original foam-extend 3.2 source code from Git and chdir to the checkout directory:
       git clone --branch v3.2 http://git.code.sf.net/p/openfoam-extend/foam-extend-3.1 foam-extend-3.2
       cd foam-extend-3.2

2. Patch the code using the patch file foam-extend-GE-OSS-3.2-win-x64.patch
       patch -p1 < foam-extend-GE-OSS-3.2-win-x64.patch

3. Due to licensing restrictions, some components cannot be shipped.
   - In ThirdParty/mingwBuild/build.sh, comment out the lines:
       build_library parmetis-4.0.3
       build_library ParMGridGen-1.0
   - Remove the following source directories:
       applications/utilities/postProcessing/dataConversion/foamToTecplot360/
       applications/utilities/surface/surfaceCoarsen/

4. Follow the procedure outlined in doc/buildInstructions/Windows/README.txt


set PATH=C:\D\dmd2\windows\\bin;C:\Program Files (x86)\Windows Kits\8.0\\\bin;%PATH%

echo dunit\assertion.d >Debug\dunit.build.rsp
echo dunit\attributes.d >>Debug\dunit.build.rsp
echo dunit\color.d >>Debug\dunit.build.rsp
echo dunit\diff.d >>Debug\dunit.build.rsp
echo dunit\framework.d >>Debug\dunit.build.rsp
echo dunit\package.d >>Debug\dunit.build.rsp
echo example.d >>Debug\dunit.build.rsp

"C:\Program Files (x86)\VisualD\pipedmd.exe" dmd -lib -g -debug -X -Xf"Debug\dunit.json" -deps="Debug\dunit.dep" -of"Debug\dunit.lib" -map "Debug\dunit.map" -L/NOMAP @Debug\dunit.build.rsp
if errorlevel 1 goto reportError
if not exist "Debug\dunit.lib" (echo "Debug\dunit.lib" not created! && goto reportError)

goto noError

:reportError
echo Building Debug\dunit.lib failed!

:noError

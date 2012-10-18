Adobe-Activator
===============
@echo off
echo Inserting into hosts file
goto HOST

:HOST
SET NEWLINE=^& echo.

FIND /C /I "activate.adobe.com" %WINDIR%\system32\drivers\etc\hosts
IF %ERRORLEVEL% NEQ 0 ECHO %NEWLINE%^127.0.0.1                   activate.adobe.com>>%WINDIR%\system32\drivers\etc\hosts

FIND /C /I "practivate.adobe.com" %WINDIR%\system32\drivers\etc\hosts
IF %ERRORLEVEL% NEQ 0 ECHO ^127.0.0.1                   practivate.adobe.com>>%WINDIR%\system32\drivers\etc\hosts

FIND /C /I "lmlicenses.wip4.adobe.com" %WINDIR%\system32\drivers\etc\hosts
IF %ERRORLEVEL% NEQ 0 ECHO ^127.0.0.1                   lmlicenses.wip4.adobe.com>>%WINDIR%\system32\drivers\etc\hosts

FIND /C /I "lm.licenses.adobe.com" %WINDIR%\system32\drivers\etc\hosts
IF %ERRORLEVEL% NEQ 0 ECHO ^127.0.0.1                   lm.licenses.adobe.com>>%WINDIR%\system32\drivers\etc\hosts

echo Host Patching complete...
goto PATCH

:PATCH
echo Detecting OS processor type
 
if "%PROCESSOR_ARCHITECTURE%"=="AMD64" goto 64BIT
echo 32-bit OS
goto END

:64BIT
echo 64-bit OS

:END
echo Everything Completed Successfully.
echo Tool Created By Damien Delay (C)2012
pause
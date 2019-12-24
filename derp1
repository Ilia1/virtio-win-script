@echo off

echo Select your OS:
echo 1) WS 2019; 2) WS 2016; 3) WS 2012 R2; 4) WS 2012; 
echo 5) W10; 6) W8.1; 7) W8; 8) W7;
echo
set /P N=Enter number:

goto :switch-%N%

:switch-1
set REL=2k19
echo %REL%
goto :switch-end

:switch-2
set REL=2k16
echo %REL%
goto :switch-end

:switch-3
set REL=2k12R2
echo %REL%
goto :switch-end

:switch-4
set REL=2k12
echo %REL%
goto :switch-end

:switch-5
set REL=w10
echo %REL%
goto :switch-end

:switch-6
set REL=w8.1
echo %REL%
goto :switch-end

:switch-7
set REL=w8
echo %REL%
goto :switch-end

:switch-8
set REL=w7
echo %REL%
goto :switch-end

:switch-end

pnputil -i -a E:\pvpanic\%REL%\amd64\pvpanic.inf
pnputil -i -a E:\netkvm\%REL%\amd64\netkvm.inf
pnputil -i -a E:\viostor\%REL%\amd64\viostor.inf
pnputil -i -a E:\vioserial\%REL%\amd64\vioser.inf
pnputil -i -a E:\vioscsi\%REL%\amd64\vioscsi.inf
pnputil -i -a E:\viorng\%REL%\amd64\viorng.inf
pnputil -i -a E:\vioinput\%REL%\amd64\vioinput.inf
pnputil -i -a E:\qxldod\%REL%\amd64\qxldod.inf
pnputil -i -a E:\qemupciserial\%REL%\amd64\qemupciserial.inf
pnputil -i -a E:\qemufwcfg\%REL%\amd64\qemufwcfg.inf
pnputil -i -a E:\Balloon\%REL%\amd64\balloon.inf
mkdir "c:\program files\balloon"
copy e:\balloon\%REL%\amd64\*.* "c:\program files\balloon\"
"c:\program files\balloon\blnsvr.exe" -i
msiexec /quiet /i E:\guest-agent\qemu-ga-x86_64.msi
echo Congratulations!
timeout /t -1

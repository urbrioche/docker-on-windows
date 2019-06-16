FROM mcr.microsoft.com/windows/servercore:1903
#nanoserver 1903 seems not have powershell
#FROM mcr.microsoft.com/windows/nanoserver:1903


COPY scripts/print-env-details.ps1 c:\\print-env.ps1

CMD ["powershell.exe", "c:\\print-env.ps1"]
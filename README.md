# Powershell-Tips
Some tips for doing stuff with powershell.

## List available modules

This gives you the modules that are already installed on your PC.
```powershell
Get-Module -ListAvailable
```

## List loaded session modules

```powershell
Get-Module
```
## List functions from a module

```powershell
Get-Command -Module [Module Name]
```
You can then call the ```Help``` command on the names of the functions displayed to read the integrated documentation.

## Download stuff

```powershell
Import-Module BitsTransfer
Start-BitsTransfer -Source $url -Destination $output
```
[Source](https://blog.jourdant.me/post/3-ways-to-download-files-with-powershell)

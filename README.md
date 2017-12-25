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

## Copying a script into multiple subdirectories

The command retrieves the child object of type directory of the current directory and stores these objects in a container.
For each of these objects you create a process:
You copy the script from the root directory to the destination classified with .FullName of the Directory object.

```powershell
Get-ChildItem -Directory . | ForEach-Object -Process { copy .\[scriptfile] -Destination $_.FullName }
```

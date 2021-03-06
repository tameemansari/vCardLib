# This project contains two sub projects

[![Build status](https://ci.appveyor.com/api/projects/status/3olgly7hvi6vfnsu?svg=true)](https://ci.appveyor.com/project/BolorunduroWinnerTimothy/vcf-reader)  [![Coverage Status](https://coveralls.io/repos/github/bolorundurowb/VCF-Reader/badge.svg?branch=master)](https://coveralls.io/github/bolorundurowb/VCF-Reader?branch=master)   [![Download VCF Reader](https://img.shields.io/sourceforge/dt/vcf-reader.svg)](https://sourceforge.net/projects/vcf-reader/files/latest/download) [![NuGet](https://img.shields.io/badge/nuget-2.1.1-blue.svg)](https://www.nuget.org/packages/vCardLib.dll) [![Mono](https://img.shields.io/badge/mono-4.4.2-ff66b6.svg)]()

## VCF-Reader

This tool was developed because I recently lost my android phone but was blessed to have created a VCF backup of all my contacts. VCF Reader loads contacts from a vCard (VCF) file into a table which allows sorting and case insensitive searching. The table shows the Surname, the first name, one email address and two Phone numbers

## vCardLib

This is the library that powers the VCF Reader. Unlike all other vCard libraries for .NET that I found, this library supports reading multiple contacts from a single vcf file and returns the contact objects in a vCardCollection. The library currently **supports only vCard version 2.1 and 3.0** (will provide a curated list of properties soon), work on adding vCard 3.0 support is ongoing.

#### How to use the library:

First get this package from nuget via your package manager:
```
Install-Package vCardLib.dll
```

Then add this using command:
```csharp
using vCardLib;
```
In your class you call the static method 'FromFile' and pass a string containing a path to it:

```csharp
string filePath = //path to vcf file;

vCardCollection contacts = vCard.FromFile(filePath);
```
 Or pass a  StreamReader object to it:
 ```csharp
StreamReader sr = //generate a streamreader somehow;
vCardCollection contacts = vCard.FromStreamReader(sr);
 ```

Iterate over the collection and pick the vCard objects:

```csharp
foreach(vCard contact in contacts)
{
  Console.WriteLine(contact.FormattedName);
}
```
complete documentation on [github.io](http://bolorundurowb.github.io/VCF-Reader/)

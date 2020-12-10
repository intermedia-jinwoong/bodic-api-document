# Tutorial 2 - Inversion of an interval (I)

// date: 2020-11-24
// http://recherche.ircam.fr/equipes/repmus/OpenMusic/user-doc/DocFiles/Tutorial/tut002/Index.html

```csharp
var originalLine = new List<int>() { 6000, 7100 };
Console.WriteLine(string.Join(", ", originalLine)); // 6000, 7100
var invertedLine = Basic.InvertPitchSequence(originalLine, originalLine[0]);
Console.WriteLine(string.Join(", ", invertedLine)); // 6000, 4900
Console.WriteLine(string.Join(", ", Conversion.IntegersToPitchStrings(invertedLine))); // C4, C#3
```


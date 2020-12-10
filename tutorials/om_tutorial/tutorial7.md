# Tutorial 7 - Expansion and compression of intervals in a sequence
// Scaling intervals of a sequence of notes by reducing or expanding each interval using arithmetical and serial operators.
// date: 2020-11-20
// http://recherche.ircam.fr/equipes/repmus/OpenMusic/user-doc/DocFiles/Tutorial/tut007/Index.html

```csharp
var sourceLine = new List<int>() { 6000, 6500, 6900, 7000 };
var expandedLine = Basic.ExpandIntervals(sourceLine, 2f);
Console.WriteLine(string.Join(", ", expandedLine)); // 6000, 7000, 7800, 8000

var compressedLine = Basic.ExpandIntervals(sourceLine, 0.5f);
Console.WriteLine(string.Join(", ", compressedLine)); // 6000, 6250, 6450, 6500
```


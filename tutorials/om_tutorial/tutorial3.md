# Tutorial 3 - Building a scale 
// date: 2020-11-24
// http://recherche.ircam.fr/equipes/repmus/OpenMusic/user-doc/DocFiles/Tutorial/tut003/Index.html

```csharp
int scaleRoot = 6000;
var intervalSeq = new List<int>() { 200, 200, 100, 200, 200, 200, 100 };
// major scale 
var cMajorScale = Basic.BuildSequenceFromDeltaValues(scaleRoot, intervalSeq);
Console.WriteLine(String.Join(", ", cMajorScale)); // 6000, 6200, 6400, 6500, 6700, 6900, 7100, 7200
```


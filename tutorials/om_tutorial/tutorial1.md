# Tutorial 1 - Note transposition

date: 2020-11-24

http://recherche.ircam.fr/equipes/repmus/OpenMusic/user-doc/DocFiles/Tutorial/tut001/Index.html

```csharp
Chord chordExample = new Chord(new List<string> { "C4", "E4", "G4", "B4" }, 1f);
Console.WriteLine(chordExample.ToBachStringPitch()); // (6000 6400 6700 7100)
chordExample.Transpose(200); // midicent 200
Console.WriteLine(chordExample.ToBachStringPitch()); // (6200 6600 6900 7300)
```


# Tutorial 5 - Retrograde transposition of notes
// date: 2020-11-13
// http://recherche.ircam.fr/equipes/repmus/OpenMusic/user-doc/DocFiles/Tutorial/tut005/Index.html

```csharp
var stringLine = new List<string>() { "C4",  "G#3", "E4", "F#5", "C5", "B4" };
var integerLine = Basic.PitchStringToInteger(stringLine);
Console.WriteLine(String.Join(", ", integerLine)); // 6000, 5600, 6400, 7800, 7200, 7100
var line = Basic.Transpose(integerLine, 200, false); // transepose by 2 semitones
line.Reverse(); //retrogade
Console.WriteLine(String.Join(", ", line)); // 7300, 7400, 8000, 6600, 5800, 6200
```


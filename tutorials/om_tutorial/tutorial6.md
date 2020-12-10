# Tutorial 6 - Four operations on a twelve-tone row
// date: 2020-11-20
// http://recherche.ircam.fr/equipes/repmus/OpenMusic/user-doc/DocFiles/Tutorial/tut006/Index.html

```csharp
// Series A1 from STRUCTURES of Pierre Boulez: { "D#5", "D5", "A4", "G#4", "G4", "F#4", "E4", "C#5", "C5", "A#4", "F4", "B3"}
var seriesA1string =  new List<string>() { "D#5", "D5", "A4", "G#4", "G4", "F#4", "E4", "C#5", "C5", "A#4", "F4", "B3" };
var seriesA1 = Conversion.PitchStringsToIntegers(seriesA1string);

// Transposition
var transposedSeriesA1 = Basic.Transpose(seriesA1, 100, false);
Console.WriteLine(String.Join(", ", transposedSeriesA1)); // 7600, 7500, 7000, 6900, 6800, 6700, 6500, 7400, 7300, 7100, 6600, 6000
Console.WriteLine("Transposed Line: ");
Console.WriteLine(String.Join(", ", Conversion.IntegersToPitchStrings( transposedSeriesA1))); // E5, D#5, A#4, A4, G#4, G4, F4, D5, C#5, B4, F#4, C4


// Retrograde
var retogradedSeriesA1 = Basic.Retrograde(seriesA1);
Console.WriteLine("Retrograded Line: ");
Console.WriteLine(String.Join(", ", Conversion.IntegersToPitchStrings(retogradedSeriesA1))); // B3, F4, A#4, C5, C#5, E4, F#4, G4, G#4, A4, D5, D#5


// Inversion
var invertedSeriesA1 = Basic.InvertPitchSequence(seriesA1, seriesA1[0]);
Console.WriteLine("Inverted Line: ");
Console.WriteLine(String.Join(", ", Conversion.IntegersToPitchStrings(invertedSeriesA1))); // D#5, E5, A5, A#5, B5, C6, D6, F5, F#5, G#5, C#6, G6

// Retrograde of the inversion
var retrogradeOfInversion = Basic.Retrograde(invertedSeriesA1);
Console.WriteLine("Retrograde of the Inversion Line: ");
Console.WriteLine(String.Join(", ", Conversion.IntegersToPitchStrings(retrogradeOfInversion))); // G6, C#6, G#5, F#5, F5, D6, C6, B5, A#5, A5, E5, D#5
```


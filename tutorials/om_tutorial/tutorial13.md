# Tutorial 13 - Random construction of a sequence II

Description
In this example we will extend our random procedure to the durations and dynamics of our sequence.

// date: 2020-11-25
// http://recherche.ircam.fr/equipes/repmus/OpenMusic/user-doc/DocFiles/Tutorial/tut013/Index.html

```csharp
(int, int) noteRange = (42, 82);
(int, int) durationRange = (10, 50);
(int, int) velocityRange = (10, 120);

var result = new Container();
int numNote = 10;
var rnd = new Random();
for (int i = 0; i < numNote; i++)
{
    var randPitch = rnd.Next(noteRange.Item1, noteRange.Item2) * 100; // * 100 for midicent
    var randDuration = rnd.Next(durationRange.Item1, durationRange.Item2) * 10;
    var randVelocity = rnd.Next(velocityRange.Item1, velocityRange.Item2);

    result.Append(new Note(randPitch, randDuration, randVelocity));
}

Console.WriteLine("llll pitch");
Console.WriteLine(result.ToBachStringPitch());
Console.WriteLine("llll duration in millisecond");
Console.WriteLine(result.ToBachStringDuration());
Console.WriteLine("llll velocity");
Console.WriteLine(result.ToBachStringVelocity());
```


# Tutorial 12 - Random construction of a sequence I, Introduction to om-random

--- Description ---
This didactic example shows the use of om-random for generating random repeated notes. We will use this function in two different ways. The first one will be for generating the pitch and the second one for generating the number for repeated notes. om-random will be used in both modes, normal mode and the eval-once mode.

// date: 2020-11-24
// http://recherche.ircam.fr/equipes/repmus/OpenMusic/user-doc/DocFiles/Tutorial/tut012/Index.html

```csharp
var result = new Container();
(int, int) randRange = (42, 82);


var rnd = new Random();
int randomPitch = rnd.Next(randRange.Item1, randRange.Item2) * 100;
for (int i = 0; i < new Random().Next(2, 6); i++)
{
    result.Append(new Note(randomPitch));
}

int randomPitch2 = rnd.Next(randRange.Item1, randRange.Item2) * 100;
for (int i = 0; i < new Random().Next(2, 6); i++)
{
    result.Append(new Note(randomPitch2));
}

int randomPitch3 = rnd.Next(randRange.Item1, randRange.Item2) * 100;
for (int i = 0; i < new Random().Next(2, 6); i++)
{
    result.Append(new Note(randomPitch3));
}

Console.WriteLine(result.ToBachStringPitch());
```
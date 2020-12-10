# Tutorial 14 - Random construction of a sequence III

Description

This patch uses omif module for conditional control with the equality test om=.

// date: 2020-11-25

```csharp
var rnd = new Random();
var result = new Container();
for (int i = 0; i < 20; i++)
{
    var caseNum = rnd.Next(0, 2);
    if (caseNum == 0)
    {
        result.Append(new Note(6000));
    }
    else
    {
        result.Append(new Note(rnd.Next(42, 82) * 100));
    }
}
Console.WriteLine(result.ToBachStringPitch());
```


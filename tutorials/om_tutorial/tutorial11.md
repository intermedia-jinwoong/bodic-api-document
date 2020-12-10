#  Tutorial 11 - Building chords starting from a harmonic spectrum

Building a chord sequence starting from a harmonic spectrum.
Description: In this example we will generate chords starting from a harmonic spectrum that we have constructed in tutorial 8 and transpose the results on different degrees (I - IV - I - V - I ). We will also play the resulting sequence thru a midi-expander using micro tuning.
// http://recherche.ircam.fr/equipes/repmus/OpenMusic/user-doc/DocFiles/Tutorial/tut011/Index.html
// date: 2020-11-24



```csharp
var arithSeq = Sequence.ArithmeticSequence(1, 16, 1);
var harmonicSeq = Sequence.HarmonicSequence(3600, arithSeq); // base note: 3600
Console.WriteLine(string.Join(" ", harmonicSeq)); // 3600 4800 5502 6000 6386 6702 6969 7200 7404 7586 7751 7902 8041 8169 8288 8400

var rnd = new Random();

(int, int) noteNumRange = (2, 5); // select the number of notes for each chord.
var result = new Container(); // creates a container which takes chords.
var progression = new List<int>() { 1, 4, 1, 5, 1 }; // I - IV - I - V - I progression

int numProgression = 1;
for (int i = 0; i < numProgression; i++)
{
    // Select N random elements from a List<T> in C# : https://stackoverflow.com/questions/48087/select-n-random-elements-from-a-listt-in-c-sharp
    // Produce a random number in a range using C#: https://stackoverflow.com/questions/3975290/produce-a-random-number-in-a-range-using-c-sharp
    var selectedNotes = harmonicSeq.OrderBy(x => rnd.Next()).Take(rnd.Next(noteNumRange.Item1, noteNumRange.Item2));


    foreach (var degree in progression)
    {
        int offset = (degree - 1) * 100;
        result.Append(new Chord(selectedNotes.Select(x => x + offset).ToList(), 1f));
    }
}
Console.WriteLine(string.Join(" ", result.ToBachStringPitch()));
```


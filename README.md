# gpiozero_pwm_buzzer
Play musical note on your Raspberry Pi using the gpiozero library.

```gpiozero_pwm_buzzer.py``` plays the musical notes on a Piezo Buzzer using ```gpiozero``` library instead of ```RPi.GPIO```

## Why PWM Buzzer?
Since we usually use a simple Piezo Buzzer for our Raspberry Pi projects, it is rather difficult to produce musical notes. 
```gpiozero_pwm_buzzer.py``` provides a simple way to play musical notes on your piezo buzzer by using Pulse Width Modulation (PWM)
to create different pitches on your buzzer.

##  Usage
There are 3 functions available starting from the lowest level:
* ```buzz(pitch, duration)```
  * Cause the buzzer to produce a buzz according to a pitch in a note frequency number (Hz)
    for a duration in seconds.
       * To produce a C4 note for half a second:
         ```buzz(261.63, 0.5)```
* ```play_note(note, beat)```
  * Cause the buzzer to produce a buzz according to a musical note in a particular
    octave for a number of beats.
    Musical note in  a particular octave is a string value **in upper case letter** followed
    by the **octave number**.
    Sharp and flat notes are represented by lower case '```b```' and '```#```' respectively.
    Duration of a beat depends on the bpm variable. Default ```bpm = 120```
    
      * To produce middle C for a beat:
        ``` play_note('C4', 1)```
      * To produce middle F# for 2 beats:
        ```play_note('F#4', 2)```
      * To produce middle B flat for half a beat:
        ```play_note('Bb4', 0.5)```
* ```play_music(scores)```
  * Buzzer will play a list of scores in string.
    To play the middle octave with sharp or flat notes for one beat each:
    ```middle_octave = ['C4:1', 'C#4:1', 'D4:1', 'Eb4:1', 'E4:1', 'F4:1', 'F#4:1', 'G4:1', 'Ab4:1', 'A4:1', 'A#4:1', 'B4:1']```
    
    ```play_music(middle_octave)```

## Credit
Special thanks to:
https://www.linuxcircle.com/2015/04/12/how-to-play-piezo-buzzer-tunes-on-raspberry-pi-gpio-with-pwm/

## License
Free to use, modify and distribute.

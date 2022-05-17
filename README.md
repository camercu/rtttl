# Ring Tone Text Transfer Language

This is just a quick demo for me to learn about RTTTL because I wanted to play
around with it on my [Flipper Zero](https://flipperzero.one/).

# Overview of RTTTL

Ring Tone Text Transfer Language (RTTTL) was developed by Nokia to be used to
transfer ringtones to cellphone by Nokia.

The RTTTL format is a string divided into three sections:
1. Name - cannot be longer than 10 characters
2. Default values - duration, octave, and beats per minute
3. Data - the "notes," where each note is specified with duration, note, octave, and optional dotting (which increases the duration of the note by one half). Duration and octave may be omitted if they are the same as default.

# References

- [RTTTL Specification](http://www.mobilefish.com/tutorials/rtttl/rtttl_quickguide_specification.html)
- [Backus-Naur notation of RTTTL spec](http://merwin.bespin.org/t4a/specs/nokia_rtttl.txt)
- [Wikipedia on RTTTL](https://en.wikipedia.org/wiki/Ring_Tone_Text_Transfer_Language)

# Flipper Zero Notes

The Flipper Zero also has a "Flipper Music Format" (`.fmf` file), which is very
similar to RTTTL. It mostly "pretty prints" the RTTTL format by breaking things
up on new lines, adding white space after commas between notes, and making the
notes be uppercase (not required).

When pulling RTTTL files from the internet, like from the [FlipperMusicRTTTL](https://github.com/neverfa11ing/FlipperMusicRTTTL)
repo, I found many of the files have the "dot" notation in the wrong location.
That is, they put the dot before the octave instead of after the octave of a note,
like it should be. This causes several notes in these songs to sound wrong.
Moving the dot to the end of each note (after the octave) fixes the audio.
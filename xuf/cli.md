# CLI

> We had a human/computer interface a hundred years before we had computers. When computers came into being around the time of the Second World War, humans, quite naturally, communicated with them by simply grafting them on to the already-existing technologies for translating letters into bits and vice versa: teletypes and punch card machines.
>
> These embodied two fundamentally different approaches to computing. When you were using cards, you'd punch a whole stack of them and run them through the reader all at once, which was called batch processing. You could also do batch processing with a teletype, as I have already described, by using the paper tape reader, and we were certainly encouraged to use this approach when I was in high school. But--though efforts were made to keep us unaware of this--the teletype could do something that the card reader could not. On the teletype, once the modem link was established, you could just type in a line and hit the return key. The teletype would send that line to the computer, which might or might not respond with some lines of its own, which the teletype would hammer out--producing, over time, a transcript of your exchange with the machine. This way of doing it did not even have a name at the time, but when, much later, an alternative became available, it was retroactively dubbed the **Command Line Interface**.
> 
> ---
> Excerpt from  *In the Beginning was the Command Line*<br>
> Neal Stephenson, 1999 (https://web.stanford.edu/class/cs81n/command.txt)

## Preface
This note is a synthesis of my understanding of Commmand Line Interfaces (CLIs), broadly construed. It is, as with all notes in this repository, neither comprehensive nor asserted to be 100% accurate, and assumes a working knowlege of CLIs as would be familiar to any developer who's ever `pip`'d, `npm`'d, or `winget`'d anything they needed on their OS of choice.

## Morse's Ghost
> \> /bin/bash

As Stephenson describes, the CLI paradigm was something of an accident, an implementation detail of distributed terminal connections that turned out to outlast the usefulness of its maternal dot-matrix printer. Numerous 'dumb' user terminals (that is: interfaces only capable transmitting & receiving data, not processing it) that once dialed in to mainframes on a college campus or company IT office demanded of a linear, conversational exchange from the standard set by telegraphy.

```
"To Mr Charlie Chaplin Sennett Studios Hollywood California congrats STOP 
Have found only person in world less funny than you STOP 
Name Baldrick STOP 
Signed E Blackadder STOP" 
Oh and put a PS: "Please, please, please STOP
```

All that really changed in the underlying protocol was was a swap out of `STOP` for `\r\n` & a more rigorous set of shorthand for a bandwidth-conscious conversation between man & machine. However, as the years went by & the chips got cheaper, the discrete mechanical implements of the teletype interface collapsed inward as the mainframe died & the CPU itself entered your office or library worksatation. To deeply understand the modern incarna`sh`ion of the CLI, therefore, requires a disentanglement of the myriad programs & protocols which have taken up the teletype's station as man-machine intermediary, if for nothing else than to clarify those workings that have become - for most intents & purposes - 90-99% invisible to even one who thinks himself comfortable in a CLI environment, as I have long imagined myself to be. 


## The Stack [DRAFT]

    1) The OS: Linux, with its programs & processes in which they run.
    2) The `sh`ell: The program that runs other programs.
    3) The `pty`s: The pseudo-terminal, a 'device' the OS provides its programs & especially shells for reading inputs (e.g. the keys you press) & writing ouputs (e.g. turning some blobs of pixels from off to on in your screen in the shapes of the letters on the keys you just pressed)
    4) `stdin`, `stdout`, `stderr`: the 3 basic senses of a program.
    5) `getty`, The Virtual Console that runs right on the machine (+ USB Keyboard / Monitor Output)
    6) GUI Terminal Emulators like `xterm` & `PuTTY.exe`
    7) Serial (Ports): Bits, Baudrates, and Betrayal
    8) TCP - Socket To ME
    9) TelNet & SSH - Reach Out & `touch` someone.
    10) Containers & Virtualization: back down the rabbit hole, the same way we came up it.

## 1. The OS: Everything, Everywhere, 64bits at once.

#TODO: Write More

##### REFS
- https://unix.stackexchange.com/questions/4126/what-is-the-exact-difference-between-a-terminal-a-shell-a-tty-and-a-con?noredirect=1&lq=1
- https://web.stanford.edu/class/cs81n/command.txt
- https://www.bbc.com/news/blogs-magazine-monitor-22953657
- https://unix.stackexchange.com/questions/21280/difference-between-pts-and-tty?rq=1
- https://docs.docker.com/reference/cli/docker/container/run/#attach
- An extensive conversation with MS Copilot on the subject (chat transcript to follow once I decide how I want to format it.)
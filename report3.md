# Lab Report 3

Are you feeling listless? Useless? Burnt out?
Do you feel like your life is an infinite cycle of feeling good, feeling alright, and then feeling like crap again?
In the end, is living just a perilous, miserable crawl through an uncaring universe until the sweet release of death?

Anyways, here's how to use *grep* in bash.

---

Today, I'm gonna teach you 4 interesting things that you can do with grep.
- You can use **regular expressions** as the argument for grep
- You can use the **-e** flag to search for multiple arguments
- You can use the **-i** flag to ignore case

And finally:
- You can use the **-v** flag to find all non-matching lines

---

## Grep with regex

Sources:
- [Grep Manual](https://www.man7.org/linux/man-pages/man1/grep.1.html)
- [Regex](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Cheatsheet)

Regex syntax gives us tools to match different strings with great precision. For example, in the 911report directory, for chapter one, we can match all of the instances of "9/11" with the command:

`grep -P "\d/\d\d" chapter-1.txt`

While grep supports regex without any flags, the type of regex it allows is *basic regular expressions*. To use the *\d* flag, you have to use the *-P* flag, signifying Perl-compatible regular expressions. The output of this command is:

```
[cs15lsp23oh@ieng6-202]:911report:197$ grep -P "\d/\d\d" chapter-1.txt  
    About five minutes after the hijacking began, Betty Ong contacted the American Airlines Southeastern Reservations Office in Cary, North Carolina, via an AT&T airphone to report an emergency aboard the flight. This was the first of several occasions on 9/11 when flight attendants took action outside the scope of their training, which emphasized that in a hijacking, they were to communicate with the cockpit crew. The emergency call lasted approximately 25 minutes, as Ong calmly and professionally relayed information about events taking place aboard the airplane to authorities on the ground.
    The airlines bore responsibility, too. They were facing an escalating number of conflicting and, for the most part, erroneous reports about other flights, as well as a continuing lack of vital information from the FAA about the hijacked flights. We found no evidence, however, that American Airlines sent any cockpit warnings to its aircraft on 9/11. United's first decisive action to notify its airborne aircraft to take defensive action did not come until 9:19, when a United flight dispatcher, Ed Ballinger, took the initiative to begin transmitting warnings to his 16 transcontinental flights: "Beware any cockpit intrusion- Two a/c [aircraft] hit World Trade Center." One of the flights that received the warning was United 93. Because Ballinger was still responsible for his other flights as well as Flight 175, his warning message was not transmitted to Flight 93 until 9:23.
    On the morning of 9/11, there were only 37 passengers on United 93-33 in addition to the 4 hijackers. This was below the norm for Tuesday mornings during the summer of 2001. But there is no evidence that the hijackers manipulated passenger levels or purchased additional seats to facilitate their operation.
    The terrorists who hijacked three other commercial flights on 9/11 operated in five-man teams. They initiated their cockpit takeover within 30 minutes of takeoff. On Flight 93, however, the takeover took place 46 minutes after takeoff and there were only four hijackers. The operative likely intended to round out the team for this flight, Mohamed al Kahtani, had been refused entry by a suspicious immigration inspector at Florida's Orlando International Airport in August.
    On 9/11, the defense of U.S. airspace depended on close interaction between two federal agencies: the FAA and the North American Aerospace Defense Command (NORAD). The most recent hijacking that involved U.S. air traffic controllers, FAA management, and military coordination had occurred in 1993.90 In order to understand how the two agencies interacted eight years later, we will review their missions, command and control structures, and working relationship on the morning of 9/11.
    FAA Control Centers often receive information and make operational decisions independently of one another. On 9/11, the four hijacked aircraft were monitored mainly by the centers in Boston, New York, Cleveland, and Indianapolis. Each center thus had part of the knowledge of what was going on across the system. What Boston knew was not necessarily known by centers in New York, Cleveland, or Indianapolis, or for that matter by the Command Center in Herndon or by FAA headquarters in Washington.   
    Controllers track airliners such as the four aircraft hijacked on 9/11 primarily by watching the data from a signal emitted by each aircraft's transponder equipment. Those four planes, like all aircraft traveling above 10,000 feet, were required to emit a unique transponder signal while in flight.
    On 9/11, the terrorists turned off the transponders on three of the four hijacked aircraft. With its transponder off, it is possible, though more difficult, to track an aircraft by its primary radar returns. But unlike transponder data, primary radar returns do not show the aircraft's identity and altitude. Controllers at centers rely so heavily on transponder signals that they usually do not display primary radar returns on their radar scopes. But they can change the configuration of their scopes so they can see primary radar returns. They did this on 9/11 when the transponder signals for three of the aircraft disappeared.
    Before 9/11, it was not unheard of for a commercial aircraft to deviate slightly from its course, or for an FAA controller to lose radio contact with a pilot for a short period of time. A controller could also briefly lose a commercial aircraft's transponder signal, although this happened much less frequently. However, the simultaneous loss of radio and transponder signal would be a rare and alarming occurrence, and would normally indicate a catastrophic system failure or an aircraft crash. In all of these instances, the job of the controller was to reach out to the aircraft, the parent company of the aircraft, and other planes in the vicinity in an attempt to reestablish communications and set the aircraft back on course. Alarm bells would not start ringing until these efforts-which could take five minutes or more-were tried and had failed.       
    Prior to 9/11, it was understood that an order to shoot down a commercial aircraft would have to be issued by the National Command Authority (a phrase used to describe the president and secretary of defense). Exercise planners also assumed that the aircraft would originate from outside the United States, allowing time to identify the target and scramble interceptors. The threat of terrorists hijacking commercial airliners within the United States-and using them as guided missiles-was not recognized by NORAD before 9/11. Notwithstanding the identification of these emerging threats, by 9/11 there were only seven alert sites left in the United States, each with two fighter aircraft on alert. This led some NORAD commanders to worry that NORAD was not postured adequately to protect the United States.
    In the United States, NORAD is divided into three sectors. On 9/11, all the hijacked aircraft were in NORAD's Northeast Air Defense Sector (also known as NEADS), which is based in Rome, New York. That morning NEADS could call on two alert sites, each with one pair of ready fighters: Otis Air National Guard Base in Cape Cod, Massachusetts, and Langley Air Force Base in Hampton, Virginia.
Interagency Collaboration. The FAA and NORAD had developed protocols for working together in the event of a hijacking. As they existed on 9/11, the protocols for the FAA to obtain military assistance from NORAD required multiple levels of notification and approval at the highest levels of government.
    In sum, the protocols in place on 9/11 for the FAA and NORAD to respond to a hijacking presumed that
    On the morning of 9/11, the existing protocol was unsuited in every respect for what was about to happen.
    The failure to find a primary radar return for American 77 led us to investigate this issue further. Radar reconstructions performed after 9/11 reveal that FAA radar equipment tracked the flight from the moment its transponder was turned off at 8:56. But for 8 minutes and 13 seconds, between 8:56 and 9:05, this primary radar information on American 77 was not displayed to controllers at Indianapolis Center.
    The defense of U.S. airspace on 9/11 was not conducted in accord with preexisting training and protocols. It was improvised by civilians who had never handled a hijacked aircraft that attempted to disappear, and by a military unprepared for the transformation of commercial aircraft into weapons of mass destruction. As it turned out, the NEADS air defenders had nine minutes' notice on the first hijacked plane, no advance notice on the second, no advance notice on the third, and no advance notice on the fourth.
    At about 9:20, security personnel at FAA headquarters set up a hijacking teleconference with several agencies, including the Defense Department. The NMCC officer who participated told us that the call was monitored only periodically because the information was sporadic, it was of little value, and there were other important tasks. The FAA manager of the teleconference also remembered that the military participated only briefly before the Pentagon was hit. Both individuals agreed that the teleconference played no role in coordinating a response to the attacks of 9/1 
. Acting Deputy Administrator Belger was frustrated to learn later in the morning that the military had not been on the call.
    United 93 and the Shootdown Order On the morning of 9/11, the President and Vice President stayed in contact not by an open line of communication but through a series of calls. The President told us he was frustrated with the poor communications that morning. He could not reach key officials, including Secretary Rumsfeld, for a period of time. The line to the White House shelter conference room-and the Vice President- kept cutting off.
    He was, and is, right. But the conflict did not begin on 9/11. It had been publicly declared years earlier, most notably in a declaration faxed early in 1998 to an Arabic-language newspaper in London. Few Americans had noticed it. The fax had been sent from thousands of miles away by the followers of a Saudi exile gathered in one of the most remote and impoverished countries on earth.
```

As you can see, the command got every instance of "9/11" in the file. Regex is very useful to precisely extract matches in ways that string literals could not.

Another example can be used in the plos file pmed.0020048.txt.

`grep -P "\s\w{10}\s" pmed.0020048.txt`

This command searches for lines with 10 character words. The output is:

```
[cs15lsp23oh@ieng6-202]:plos:204$ grep -P "\s\w{10}\s" pmed.0020048.txt
        Current journal requirements forcing clinical trials to be registered [1] are
        to a journal. Most of the patients consenting to clinical trials do so out of altruism. It
        altrusitic instincts, similar to money in public charities, are not proprietary
        information, nor can physicians cash out the trust of their patients. In reality, it is the
        inform future research and help smaller, innovative companies avoid redundancy. Voluntarily
```

Again, regex is useful because it can support more advanced searches, like the amount of characters that are in a word.

---

## The -e flag

Source: [Grep Manual](https://www.man7.org/linux/man-pages/man1/grep.1.html)

The *-e* is usually redundant. For example, on the same plos file, using 
`grep -e "innovative" pmed.0020048.txt` and `grep "innovative" pmed.0020048.txt` 
give the same output:

```
[cs15lsp23oh@ieng6-202]:plos:206$ grep -e "innovative" pmed.0020048.txt
        inform future research and help smaller, innovative companies avoid redundancy. Voluntarily
```

```
[cs15lsp23oh@ieng6-202]:plos:207$ grep "innovative" pmed.0020048.txt    
        inform future research and help smaller, innovative companies avoid redundancy. Voluntarily
```

However, the power of the *-e* flag comes when you use multiple arguments:

`grep -e "innovative" -e "consenting" pmed.0020048.txt`

That causes the command to return lines that match either of the arguments:

```
[cs15lsp23oh@ieng6-202]:plos:208$ grep -e "innovative" -e "consenting" p
med.0020048.txt
        to a journal. Most of the patients consenting to clinical trials do so out of altruism. It
        inform future research and help smaller, innovative companies avoid redundancy. Voluntarily
```

Therefore, the *-e* command is useful to find instances of different arguments. With this combined with regex, the grep command becomes very, very useful for searching through files.

# The -i flag

Source: [Grep Manual](https://www.man7.org/linux/man-pages/man1/grep.1.html)

The *-i* flag is the ignore case flag. This flag is fundamental for the grep command because you might not know if a word is capitalized or not in a file.

For example, using this command:

`grep -i current pmed.0020048.txt`

You can find instances of "current", regardless of the case:

```
[cs15lsp23oh@ieng6-202]:plos:210$ grep -i current pmed.0020048.txt      
        Current journal requirements forcing clinical trials to be registered [1] are
        (currently being battered for greed) and attract a more talented workforce, and may even
        help the current efforts to reform the tort law.
```

In a different file (pmed.0020047.txt), you can do the same thing with this command:

`grep -i society pmed.0020047.txt`

To get this output:

```
[cs15lsp23oh@ieng6-202]:plos:214$ grep -i society pmed.0020047.txt      
        same place. Society should recognize that funding university research through patents is
        are all based on the same fundamental principle: knowledge contributes to society when it
```

The *-i* flag is useful for being thorough in your search. It removes uncertainty: if you don't know exactly what the string is going to look like, you can cover for different options.

---

# The -v flag

Source: [Grep Manual](https://www.man7.org/linux/man-pages/man1/grep.1.html)

The *-v* flag returns all lines that DON'T match the provided argument(s). This is useful for filtering out certain things in a file that you don't need.

`grep -v the pmed.0020048.txt`

This command returns all the lines that don't include "the". As expected, it's not that many lines:

```
[cs15lsp23oh@ieng6-202]:plos:215$ grep -v the pmed.0020048.txt





        Current journal requirements forcing clinical trials to be registered [1] are
        filed in a central (online) repository. The primary data should also be required to be in
        altrusitic instincts, similar to money in public charities, are not proprietary
        inform future research and help smaller, innovative companies avoid redundancy. Voluntarily
        (currently being battered for greed) and attract a more talented workforce, and may even
```

This next command returns all the lines that don't include "data":

`grep -v data pmed.0020048.txt`

Output:

```
[cs15lsp23oh@ieng6-202]:plos:217$ grep -v data pmed.0020048.txt





        Current journal requirements forcing clinical trials to be registered [1] are
        insufficient and are unlikely to solve the problem of negative trials never even making it
        to a journal. Most of the patients consenting to clinical trials do so out of altruism. It
        institutional review boards refuse to allow human experimentation unless the protocol is
        the public domain (say, within 1–2 years after completion). Data obtained by appealing to
        altrusitic instincts, similar to money in public charities, are not proprietary
        information, nor can physicians cash out the trust of their patients. In reality, it is the
        inform future research and help smaller, innovative companies avoid redundancy. Voluntarily
        sticking to higher standards of ethics will raise societal respect for the industry
        (currently being battered for greed) and attract a more talented workforce, and may even
        help the current efforts to reform the tort law.
```

This command is important to improve the flexibility of *grep*. Filtering out certain arguments is useful in certain situations where you don't want to see certain things in a file.

---

In conclusion, 

uh...
yeah.

I got nothing.


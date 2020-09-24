---
layout: default
title: about
permalink: /about/
page-category: not-indexed
---

---

## The school years

I remember spending hours and hours reading the very formidable collection of science magazines that I had at home growing up. These included such relics as Vietnam war era ["Popular Mechanics"][pop-mech-cover-june-67] and "Popular Science," (probably something to do with my great grandfather moving to Canada in 1909) filled with articles and colorful pictures of the latest war hardware, like [fighter aircraft][pop-mech-1966-us-af] and [guns][pop-mech-1975-guns], in addition to regular science articles about space, apollo missions etc., alongside [DIY carpentry projects][pop-mech-1967-bed] and reviews of latest cars/[RVs][pop-mech-1975-rv]. There were also Indian magazines such as "Science Today" and "Science Reporter." I still remember many things from hundreds of articles I read, like one titled "SST: Super Sonic Transport," about the Concorde and the Russian Tu-144 SSTs. In one of these magazines was an article about putting together a crystal radio. Old timers might identify with this being one of the rites of passage of becoming a geek. My first attempt was a failure. I found a silicon diode and tried to use it as a detector not realizing that the the diode made an excellent rectifier but dropped 0.6 volts across it, making it wholly unsuitable for a crystal radio. Also, the nearest radio station was too far. In another year or so, I'd move to Delhi and much closer to high power radio stations of upto a Megawatt and an OA79 germanium detector diode perfect for use in a crystal radio would come into my posession. 

## The electronics years

[The crystal radio consisted of][crystal-radio-image] a ferrite rod about 12" long wound with what was probably an AWG 16 single strand enameled copper wire, a fairly typical vintage 500pf air gap variable capacitor, and OA79 detector diode connected to a high impedence (3k ohms) magnetic headphones. I was ecstatic when it tuned to 666 MHz All India Radio for the first time (AM radio stations in India are at multiples of 9 KHz instead of 10 as in US). The antenna was a long wire of about 10 meters length, enough to collect energy to actually light up a red L.E.D. and I was, from then on, hooked to electronics. The raw material came from the flea market that assembled every Sunday behind the Red Fort in Delhi. There were discarded radios and other analog and digital hardware from consular and military scrap. PCBs full of transistors and passive devices could be had for a few rupees (or dimes). It was like being a kid in a candy store. Soon, I was assembling and taking apart audio amplifiers, electronic doorbells, radio transmitter and receivers and other weird gadgets as the one which gave a mild electric shock to anyone who held it, using only a battery, a motor and a transformer, unsurprisingly called a "Tickle Generator" or something. I can still read many of the canonical color coded resistor values while half asleep.

Having a long wire antenna also enabled Dx'ing - listening to distant radio stations. I listened everyday to the BBC transmission from Oman at 1413 MHz that is appently still in service. On short wave, transmissions from Europe, Africa, Asia and Australia were reliably heard, for example, Radio France International on 16m band from Gabon, Africa, Radio Pyongyang, [Radio Prague][qsl-radio-prague-front], Deutsche Welle, Radio Berlin (East Germany), [Radio Japan][qsl-radio-japan-front] [(#2)][qsl-radio-japan2-front], US DOD Armed Forces Radio from Philipines [(front)][qsl-radio-dod-front], [(and back)][qsl-radio-dod-back] etc. If you wrote to these radio stations with a report on signal reception conditions, they would send you an official confirmation on a postcard called a QSL card. I collected dozens of these from various broadcasters, the notable being from [Radio Luxembourg][qsl-radio-luxembourg-front], [Radio Monte-Carlo][qsl-radio-montecarlo-front], [Radio Sweden][qsl-radio-sweden-front] and [Radio Mediterranean][qsl-radio-mediterranean-front] on the medium wave band. These usually required being awake at 3:30 - 4:30 in the morning for favorable ionespheric propagation (E layer over darkness during winter, post-dusk in Europe and pre-dawn in India). [The Radio Sweden jingle][radio-sweden-jingle] was the most exciting, albeit somewhat haunting, [interval music I ever heard on Radio][shortwave-many-jingles], the first time I heard it at 5AM after DX'ing the entire night. As a side effect of all this, my English became a lot better.

When I started attending Delhi University, the projects grew more complex. I'd help the final year students put together electronics projects for graduation credits. Over three years, I must have helped put together dozens of these electronic projects, including one I designed for line of sight audio commmunication link using infra red LED and sensor using simple amplitude modulation. I had also started building digital projects using counters (flip flops) and simple gates in TTL logic. A 555 timer IC and 741 op-amp were staples. My own final year projects were a [transistor V-I curve tracer][xtor-i-v-curve] that displayed eight curves at the same time on an oscilloscope with different base currents using persistence-of-vision and an analog multimeter with active circuitry for a very high impedence input (using a CMOS FET op-amp called 3140).

## The programming years

I started attending the premier Indian Institute of Science in Bangalore for a master's degree in Electronic Communication Engineering. The first course in programming called "Introduction to Programming" was a trial by fire. The first assignment after couple of weeks of instruction, when I hadn't even touched a computer before, was to write a simple simulator/assembler in Pascal for a computer that could execute 12 machine instructions like ADD,MOV,SUB,JMPZ (jump if zero) etc. This was to be done on an HP mini running Unix with a VT100 terminal.  The second assignment after a month or so was to write a primitive LISP REPL interpreter. Needless to say, this was way too much for me to handle and I dropped the course to retake it during summer by which time I was slightly better prepared, learnt to use an IBM PC clone at 4.77 MHz and dual 5" floppy drives, did [write the LISP REPL][lisp] and managed to get the best possible grade. I wanted to take an Amateur radio exam that needed proficiency in Morse code at 12 words per minute and soon I was writing my first "App" using Borland Turbo-Pascal under DOS to practice Morse code. I had a set of drop down menus using text based graphics, where I could choose the set of characters, their duration and spacing for practice; looked quite professional I think. I cleared the 12 wpm test administered by the Govt. of India and still [have the paper that says so][minofcomm]. Later, I took more courses on Data structure and algorithms using C language, and audited courses on operating systems and computer architecture. In all, while at IISc, I took 35 courses spanning electrical machines, analog and digital electronics, computing, networks, optical and microwave communications, radars, DSP, VLSI and mathematics including one called "Computational methods of Non-linear optimization." In this course, I got 16 marks out of 100 and an A-grade. 1/100 was passing grade and four students couldn't make it, as far as I remember. I learnt a lot about a lot of things over four years. My final year project was thousands of lines of C-code including lex/yacc tools and graph algorithms [shudder]. I stayed at the top of my class for all seven years of college.

## The work years

I have worked mostly in CMOS circuit design and ASIC physical design. I contributed to many products that successfully made it to the market. These included fast SRAM memories, microprocessors (Intel Pentium III, Sun UltraSparc III, Transmeta Efficeon) and pioneering ASICs (MiMo Wifi, 10GBase-T Phy, SSD PCIE controller, Active Silicon Interposer). [See more on my resume.][resume]

## Machine Learning

One day while browsing the Coursera website, not sure what I clicked, I landed on a screen that congratulated me on registering for Prof. Andrew Ng's Machine Learning course. Fearing unimagined consequences for not continuing, I started the course and completed the first week in 4 days, the second in three and totally got into it.By the time I reached the last weeks, I was doing one week per day. I was happy with what I learnt, but somewhere along the course Prof Ng, mentioned something about maximal likelihood estimate and said not to worry if I didn't understand statistics. Soon, I had finished a set of 10 courses on statistics from John Hopkins. But, what is statistics without lot of data....and I then completed a specialization on Big Data from UC San Diego, which also made me buy, so that I could run big data assignments, a 24-core, 48GB server for $200 from Ebay. I did about 22 courses in 5 months and unsurprisingly damaged my back and was mostly bed ridden for few months. More recently, I completed the five course specialization on Deep Learning also taught by Prof Andrew Ng. and acquired a better computer, the kind where the GPU consumes more power than the CPU. I worked as consultant in 2016/2017 on a silicon design project. Also, doing not so great on [Kaggle][kaggle]. I'm currently working as a hardware design engineer at a machine learning chip startup.

[resume]: {{ site.url }}/resume/
[kaggle]: https://www.kaggle.com/gary347
[lisp]: https://github.com/swiftgurmeet/prehistoric/blob/master/lisp.c
[radio-sweden-jingle]: https://www.youtube.com/watch?v=_QhzQYKFOlU
[shortwave-many-jingles]: https://www.youtube.com/watch?v=hFRYKDF2kxs&t=185s
[crystal-radio-image]: {{ site.url }}/images/crystal-radio.jpg
[qsl-radio-sweden-back]: {{ site.url }}/qsl/radio-sweden-back.jpg
[qsl-radio-sweden-front]: {{ site.url }}/qsl/radio-sweden-front.jpg
[qsl-radio-japan-back]: {{ site.url }}/qsl/radio-japan-back.png
[qsl-radio-japan-front]: {{ site.url }}/qsl/radio-japan-front.png
[qsl-radio-mediterranean-back]: {{ site.url }}/qsl/radio-mediterranean-back.png
[qsl-radio-mediterranean-front]: {{ site.url }}/qsl/radio-mediterranean-front.png
[qsl-radio-luxembourg-back]: {{ site.url }}/qsl/radio-luxembourg-back.png
[qsl-radio-luxembourg-front]: {{ site.url }}/qsl/radio-luxembourg-front.jpg
[qsl-radio-montecarlo-front]: {{ site.url }}/qsl/radio-montecarlo-front.jpg
[qsl-radio-prague-front]: {{ site.url }}/qsl/radio-prague-front.jpg
[qsl-radio-norway-front]: {{ site.url }}/qsl/radio-norway-front.jpg
[qsl-radio-korea-front]: {{ site.url }}/qsl/radio-korea-front.jpg
[qsl-radio-dod-front]: {{ site.url }}/qsl/radio-dod-front.jpg
[qsl-radio-dod-back]: {{ site.url }}/qsl/radio-dod-back.jpg
[qsl-radio-japan2-front]: {{ site.url }}/qsl/radio-japan2-front.jpg
[qsl-radio-kol-front]: {{ site.url }}/qsl/radio-kol-israel-front.jpg
[qsl-radio-rsa-front]: {{ site.url }}/qsl/radio-south-africa-front.jpg
[pop-mech-cover-june-67]: {{ site.url }}/images/pop-mech-cover-06-1967.jpg
[pop-mech-1966-us-af]: {{ site.url }}/images/pop-mech-1966-us-af.jpg
[pop-mech-1967-bed]: {{ site.url }}/images/pop-mech-1967-bed.jpg
[pop-mech-1975-rv]: {{ site.url }}/images/pop-mech-1975-rv.jpg
[pop-mech-1975-guns]: {{ site.url }}/images/pop-mech-guns-1967.png
[xtor-i-v-curve]: {{ site.url }}/images/xtor-i-v-curve.gif
[minofcomm]: {{ site.url  }}/st/min-of-comm-ham.pdf


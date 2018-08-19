---
title: "Water Flow Monitoring"
date: "2018-08-18"
draft: false
---

I recently had a large water leak due to my pool autofill solenoid breaking so
I belatedly decided to finish a project that I'd started some years earlier
to monitor my home water usage and generate alerts if the flow or usage became
excessive.

The system is simple and consists of a water meter with a reed switch
pulse counter and a raspberry pi with a [piface 2](http://www.piface.org.uk/products/piface_digital_2/).

![Meter](/images/meter.jpg)
![RPI](/images/rpi.jpg)


The reed switch outputs from the meter are connected directly to the inputs on
the piface 2 (the red and white wires on the right hand side). The software I
wrote [pulsemon](https://github.com/cosnicolaou/go/tree/master/cmd/pulsemon)
can also forward the pulses received over a relay to another monitoring
system (the black and white wires) such as an irrigation controller.

The reed relay is just a switch that's closed magnetically when one of the dials
on the meter crosses zero. In the DLJ meter I have the 10 gallon dial is used
so there's a pulse for every 10 gallons. The switching is slow in the sense that
once the switch is closed it stays closed for a while until the dial rotates away
far enough to for it to be out of range of the magnetic field and to close; this
can be on the order of a minute or more for a low flow rate. The pulsemon
app is written in [go](https://golang.org) and polls the specified input
pin and can mirror that input either to a relay or a CMOS switch output. It's
configured via a json file and can send email when certain flow rate is
exceeded as well as a periodic email showing dailing usage. It also writes a
timestamp to a log file every thime that it reads a pulse. This can be
postprocessed to compare against a monthly bill for example.

I use [hypriot](https://hypriot.com) as the OS for my pis and deploy this app
as a container.


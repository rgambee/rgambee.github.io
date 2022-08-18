# Hackathon Projects

Formlabs, [my employer](/job.html), holds an annual hackathon for its
employees where individuals or small groups work on a project of their choosing
for a few days. I've participated in every one and had a blast each time. Here
are a couple of the most successful projects.

Unfortunately, I can't share any pictures or code since they contain
proprietary information.

## 2021: Live Dashboard for Sensor Data

The hackathon project I'm most proud of was the one I did in 2021, which was my
only solo project. I created a dashboard for viewing live sensor data and
status information from our 3D printers in a web browser. Formlabs already
provides a dashboard for our customers to monitor the status of their printers.
I wanted to create an internal tool to give engineers like myself an under-the-
hood view to help debug issues and improve performance.

The project involved both embedded and web development. The server running on
the printer was written in Go and streamed data to clients using WebSockets.
Visualization on the client end was done in JavaScript using [plotly.js
](https://plotly.com/javascript). It took a lot of work, but I managed to
complete all the features I wanted to in four consecutive days.

### Design Principles

Before starting the project, I had a clear set of principles in mind to guide
the design. Writing these down ahead of time was a major reason the project was
as successful as it was.

My primary principle was that I wanted the burden of running the server on the
printer to be minimal in terms of CPU, memory and disk I/O. The printer has
more important work to worry about, like driving its motors and laser. The
project would have been nearly useless if it negatively impacted the active
print since hardly anyone would have wanted to use it.

For similar reasons, I wanted the server running on the printer to be fully
stand-alone and self-contained. I didn't want to make any modifications to the
existing applications in the firmware that are responsible for running prints.

Thirdly, I wanted it to be as simple as possible to fire up the tool and use
it, even for a brand new employee without much software knowledge. I didn't
want them to have to run any scripts or install any packages.

Lastly, I deliberately avoided any way of controlling the printer from the
dashboard. Being able to remotely start and stop prints, or even move motors,
would certainly have been handy. But it might have made people hesitant to
adopt the tool if there was a risk of someone accidentally ruining their
important test print. This principle also helped limit the scope of the initial
feature set. Controls, with appropriate safeguards, could always have been
added later.

### Features

The dashboard showed plots of motor positions, temperatures and other sensor
data, all of which updated in real time. It also displayed information about
the active print, including its name, layer number and time remaining.

The backend could have been expanded to capture other information relatively
easily. The limitations were on the frontend. I didn't want the UI to become
too cluttered. Plus, the graphs were starting to stutter when updating three
different plots, each with multiple series, ten times a second. To address
this, I later added the ability to toggle off undesired plots to save bandwidth
and client CPU usage.

The dashboard was compatible with all our printers at the time: the Form 3,
Form 3L and Fuse 1. It adjusted which plots were displayed based on the printer
type since different products have different sensors.

### Implementation

The backend was written completely in Go, which isn't exactly the most common
language for web development. My preferred language is Python, but I went with
Go because I wanted minimize the CPU and memory impact on the printer. I had
first learned Go a few years prior during [Advent of Code](/projects/aoc.html),
but this was my first practical project with it. I found it easier than I
expected to collect sensor data and push it to clients over WebSockets. Thank
you to the authors of the libraries I used! And Go definitely fit the bill when
it came to performance. In my testing, the server never used more than a few
percent of the printer's CPU or memory, even with several clients connected.

In accordance with the third design principle, the dashboard was extremely
simple to view. All a user had to do was open a web browser and type in the
printer's IP address. The server was configured to start automatically when the
printer booted up, and it listened on the default HTTP port of 80. Once a
client connected, the server would set up a WebSocket to stream data
continuously.

Every time the client received a message from the server, about 10 times a
second, it would update the plots accordingly. Plotly makes it possible to
modify individual elements of a plot without needing to redraw the whole thing,
which is very helpful when making live dashboards like this one. However, the
visualizations started to become a little jittery once I was plotting many
different data steams. Had I wanted to add more, I would have explored other
libraries besides plotly. That said, plotly excelled in the number and
customizability of the visualizations it offered.

The hardest part for me by far was fiddling with the HTML and CSS to make it
look presentable. That alone took me an entire day out of the four I spent on
the project. I'm satisfied with the final appearance, but I'm sure someone with
more experience with web UIs could give me lots of pointers to make it better.

### Response

The response from my coworkers was extremely positive. Several told me how
useful this would be in their day-to-day work. I even got a shout out from the
CEO in the wrap-up email!

Ultimately, the tool was not widely adopted for a combination of reasons. The
products it was written for were already mature at the time, with the bulk of
their engineering effort behind them. The next generation of products, while
timed well to take advantage of this tool, turned out to be substantially
different in terms of their firmware. The server portion would have needed to
be rewritten from scratch. But don't despair! The spirit of a dashboard for
viewing live sensor data is still alive and well, just in a different form.
And even though it fell short of being a smash hit, I'm proud of the
programming and project planning skills it taught me.

### Name

I named the project Tirmo, which [means "watcher"
](https://www.elfdict.com/w/tirmo/q) in JRR Tolkien's Elvish language of
Quenya. Formlabs has a history of using Tolkien-themed names internally, and I
felt that the meaning was a good fit. It's also concise, memorable and
relatively easy to spell and pronounce, at least as far as Elvish goes!

## 2016: Top-Down <abbr title="Stereolithography Apparatus">SLA</abbr> 3D Printer

For my first hackathon, I worked with three others to make one of our 3D
printers print upside-down (in a loose sense). Formlabs printers hold liquid
resin in a clear-bottomed tank and cure it with UV light from below, a
technique known as bottom-up or inverted stereolithography. An alternative
approach is to cure the resin from above. This has the advantage of exerting
much lower force on the part as it prints, though it suffers from challenges
with surface tension, among others.

<figure>
    <img
      class="centered"
      src="/media/slaComparison.svg"
      alt="Diagram showing basics of stereolithography 3D printing"
      style="width: 80%;"
    >
    <figcaption>
      Comparison of bottom-up and top-down stereolithograpy
    </figcaption>
</figure>

I helped with calibrating the printer and generating the instructions to make
it print. The printing process was quite different from what we were used to,
but we managed to get our first print started in under 24 hours! It was fun to
squeeze as much of a product cycle as we could into only a few days.

### Calibration

By moving the optics from the bottom of the printer to the top, we changed the
path length of the laser. We therefore needed to adjust the relationship
between laser beam angle, which is what the printer controls, and linear
distance at the print plane, which is what the user cares about. Dimensional
accuracy wasn't a priority for us, so we measured the angular distances between
a few points of known linear distance. Then we simply scaled the original
calibration to compensate.

We also needed to adjust the vertical distance between the motor's home
position and the surface of the resin. That was as simple as filling the tank
to the desired level, lowering the Z stage to the correct height, and recording
its position.

### Printing Process

The biggest challenge for us in terms of the printing process was surface
tension. Bottom-up printers don't need to worry much about this, though they
certainly have other problems like suction forces. Top-down printing happens at
an air-liquid interface, where surface tension has a large impact. Resin tends
to bead up instead of forming a uniform layer.

We overcame this by submerging the part far enough for gravity to overcome
surface tension. However, this then required waiting for that excess resin to
flow off after raising the part back up to the correct height for the next
layer. Industrial top-down printers often have a wiper that sweeps across to
create a uniform layer of liquid resin. And I'd wager they tune the resin
formulation to control the surface tension.

The time when surface tension is most apparent is at the very start of the
print when the entire Z stage needs to be submerged just a fraction of a
millimeter below the resin surface. Waiting for the resin to settle out can
take a long time, so we used a perforated Z stage. The holes allowed resin to
flow through the middle of the Z stage instead of needing to go all the way to
the outside edge. This saved several minutes off the start of every print. A
perforated or slotted Z stage also has benefits in bottom-up printing, but the
main downside in both cases is that it's messy.

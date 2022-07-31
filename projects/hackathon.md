# Hackathon Projects

Formlabs holds an annual hackathon for its employees where individuals or small
groups work on a project of their choosing for two to three days. I've
participated in every one and had a blast each time. Here are a couple of the
most successful projects.

Unfortunately, I can't share any pictures or code since they contain
proprietary information.

## 2016: Top-Down SLA 3D Printer

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

## 2021: Live Sensor Data Visualization

The hackathon project I'm most proud of was the one I did in 2021, which was my
only solo project. I created a dashboard for viewing live sensor data and
status information from our 3D printers in a web browser. It involved both
embedded and web development. The server running on the printer was written in
Go and streamed data to clients using WebSockets. Visualization on the client
end was done in JavaScript using plotly. It took a lot of work, but I managed
to complete all the features I wanted to. The hardest part for me by far was
fiddling with the HTML and CSS to make it look presentable.

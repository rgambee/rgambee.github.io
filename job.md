# Professional Experience

## FutureSearch: AI Research Engineer (2025 to Present)

[FutureSearch](https://futuresearch.ai/) is a startup leveraging AI to answer
tough questions, including market research and forecasting the future. I joined
as an AI Research Engineer in 2025. [See here](https://evals.futuresearch.ai/)
learn more about our research.

## Formlabs: Systems Integration Engineer (2015 to 2025)

Based in Somerville, Massachusetts, [Formlabs](https://formlabs.com/) designs
professional-grade 3D printers. Unlike most 3D printers which extrude filament
through a heated nozzle (fused deposition modeling or FDM), Formlabs printers
use light to solidify either liquid resin (stereolithography or SLA) or plastic
particles (selective laser sintering or SLS) into complex objects. These
optical techniques can provide better surface finish, finer detail and superior
mechanical properties compared to FDM.

We were the first to bring stereolithography to the desktop with the
Form&nbsp;1. Since then, with the release of the Form&nbsp;2, 3 and 4, we have
become the all-time top seller of professional 3D printers.

<figure>
  <img
    class="centered"
    src="/media/Form4_and_Form4L.png"
    alt="Form 4 and Form 4L 3D printers"
    style="width: 100%;"
  />
  <figcaption>
    The Form&nbsp;4 (left) and the Form&nbsp;4L (right).
    Image courtesy of Formlabs.
  </figcaption>
</figure>

I work on the Systems Integration team, which operates at the intersection of
mechanical, electrical and software engineering. We are responsible for
assembling the printer's many subsystems into a reliable, well-oiled machine.
The team is highly interdisciplinary, taking on different responsibilities
during the product's development cycle.

During the early stages, we design and prototype new subsystems to determine
what the final product will look like. This requires close collaboration with
other engineering teams, from hardware to software. Early in the Form&nbsp;4
prototype phase, I was the lead architect and developer of the core firmware
application for running 3D prints. Written in Python, the application had to
precisely move motors and time UV exposure to successfully produce parts. It
also needed to monitor a myriad of sensors to maintain a suitable printing
environment, as well as log data to answer key questions about the new hardware
design. And it had to be easily extensible so that new features could be quickly
added in response to the needs of the project.

As the new printer moves towards production, the Systems Integration team
focuses on maximizing reliability to deliver the best experience to our users.
I designed a system to robustly manage the data stored on the Form&nbsp;4's
user-replaceable components, such as the resin tank and cartridge. This system
needed to gracefully handle read and write failures, since the communication
protocol was noisy and the user could remove the component at any time. It had
to perform exhaustive security and validation checks to protect Formlabs'
primary revenue stream from counterfeits. And it needed to be easily extendible
to other data formats and storage media.

Our work doesn't stop once printers have made their way into customers' hands.
We listen to feedback from our users and continue to make improvements that can
be deployed via software updates. For instance, not long after shipping the
Form&nbsp;3, we uncovered an issue with the its resin level sensor. Even though
it only affected a small proportion of printers, those who were impacted had a
risk of their prints failing due to lack of resin. To avoid returning the
printers for repair, which would have inconvenienced our customers and cost us
money, I developed a firmware solution that saved both time for our users and
money for Formlabs.

Every year, Formlabs runs a hackathon for all employees. You can read about a
few of the [fun projects I've worked on](/projects/hackathon.html).

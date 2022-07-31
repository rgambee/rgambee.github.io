# Professional Experience

### Formlabs: Systems Integration Engineer (2015 to Present)

Based in Somerville, Massachusetts, [Formlabs](https://formlabs.com/) designs
professional-grade 3D printers. Unlike most 3D printers which extrude filament
through a heated nozzle (fused deposition modeling or FDM), Formlabs printers
use a laser to solidify either liquid resin (stereolithography or SLA) or nylon
particles (selective laser sintering or SLS) into complex objects. These
laser-based techniques can provide better surface finish, finer detail and
superior mechanical properties compared to FDM. We were the first to bring
stereolithography to the desktop with the Form 1, and its successors, the Form
2 and Form 3, are widely regarded as the best desktop stereolithography
printers on the market.

<figure>
    <img
      class="centered"
      src="/media/Form3_and_Form3L.webp"
      alt="Form 3 and Form 3L 3D printers"
      style="width: 100%;"
    >
    <figcaption>
      The Form 3 (left) and the Form 3L (right). Image courtesy of Formlabs.
    </figcaption>
</figure>

I work on the Systems Integration team, which operates at the intersection of
mechanical, electrical and software engineering. We are responsible for
assembling the printer's many subsystems into a reliable, well-oiled machine.
The team is highly interdisciplinary, taking on different responsibilities
during the product's development cycle. During the early stages, we design and
prototype new subsystems, which includes consulting with hardware engineers to
select components and collaborating with software developers to incorporate
each system into the firmware. When developing the Form 3 resin level sensor, I
narrowed down a list of nearly a dozen options to find which would be most
suitable by balancing accuracy, cost and user experience. Once one had been
selected, I wrote the code to integrate the sensor into the printing
process&mdash;code that's running on tens of thousands of printers all across
the world at any given moment.

As the new printer moves towards production, the Systems Integration team
oversees extensive validation and lifetime testing to ensure each element
performs as expected. We also help to diagnose and resolve issues that arise at
the factory during assembly and calibration. For our Form 3L printer, I led the
effort to address problems with the optical system that were limiting
throughput on the line. The optics of the Form 3L are particularly challenging
because it has two lasers which need to be calibrated to one another very
accurately in order to eliminate artifacts where they meet. Thanks to my
contributions, we were able to increase yield significantly and ship printers
to customers more quickly.

Our work doesn't stop once printers have made their way into customers' hands.
We listen to feedback from our users and continue to make improvements that can
be deployed via software and firmware updates. For instance, not long after
shipping the Form 3, we uncovered an issue with the its resin level sensor.
Even though it only affected a small proportion of printers, those who were
impacted had a risk of their prints failing due to lack of resin. To avoid
returning the printers for repair, which would have inconvenienced our
customers and cost us money, I developed a firmware solution that saved both
time for our users and money for Formlabs.

Every year, Formlabs runs a hackathon for all employees. You can read about a
few of the [fun projects](/projects/hackathon.html) I've worked on.

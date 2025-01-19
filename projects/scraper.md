# AI-Powered Web Scraper

[**GitHub Repository**](https://github.com/AI-Governance-Safety-Canada/content-scraping)

In the fall of 2024, I volunteered for [AI Governance & Safety](https://aigs.ca)
(AIGS), a Canadian non-profit working to ensure that advanced AI is safe and
beneficial for all. It was an amazing opportunity for me to expand my portfolio
while helping an effective organization contribute to arguably the most pressing
issue of our time.

## Problem Statement

AIGS maintains a list of relevant events which their community may wish to
attend. These events are held by a variety of organizations and range from
conferences to webinars. Originally, the team compiled events by checking a list
of websites one by one and manually entering relevant ones into a database.

This process is time-consuming and doesn't scale well: each new website they
check requires more effort. As a small team who have their hands full, they
wanted an automated solution.

## Objectives

When designing a solution, there were several criteria I took into account:

1.  Scalable
    -   Unlike the manual system, it should be as easy as possible to fetch
        events from a new website.
1.  Maintainable
    -   The solution needs to keep working with minimal upkeep.
    -   If it breaks whenever a website changes its layout, then it's not doing
        its job of saving time.
1.  Extendable
    -   It should be feasible to extend the system to collect other types of
        information, such as relevant publications.
1.  Affordable
    -   AIGS is a small non-profit with limited resources.
    -   The more they spend on compiling events, the less they have to spend on
        other initiatives.

## Design

I considered several approaches and scored them according to the criteria above.
The top scoring one was AI-powered web scraping, which leverages a large
language model to parse webpages and extract the relevant information.

| Approach                       | Scalable | Maintainable | Extendable | Affordable |
| ------------------------------ | :------: | :----------: | :--------: | :--------: |
| Existing Manual Process        |    -     |      +       |     +      |     -      |
| Traditional Web Scraping       |    -     |      -       |     -      |     +      |
| Zero- or Low-Code Web Scraping |    +     |      +       |     +      |     -      |
| AI-Powered Web Scraping        |    +     |      +       |     +      |     +      |

## Details

After experimenting with multiple AI scraping services, I settled on OpenAI's
API due to its reliability and ease of use. I
[used the Pydantic library](https://github.com/AI-Governance-Safety-Canada/content-scraping/blob/cf4161d6fd18b2de9539687d6a4b419e748dcb72/scraper/events/event.py)
to dictate the information I wanted for each event, validate the model
responses, and serialize the information for writing to a file. I iterated on
the prompt several times to direct the model to output all relevant details in
the desired format without hallucinating.

Most organizations list their events on a single overview page, with each event
linking to its own detailed page. To reliably capture all the information, I
implemented a
[two-stage solution](https://github.com/AI-Governance-Safety-Canada/content-scraping/blob/cf4161d6fd18b2de9539687d6a4b419e748dcb72/scraper/events/pipeline.py).
I first scrape the overview page to find all events and then visit each event's
specific page to gather additional details. Here's a summary of the logic:

- For each overview page in the list of organizations
    - Fetch the page's contents
    - Clean the contents to remove irrelevant sections
    - Parse the contents using the language model
    - For each event found by the model
        - Fetch the contents of the event-specific page
        - Clean the contents to remove irrelevant sections
        - Parse the contents using the language model
        - Combine the information from the overview and event-specific pages
        - Save the event to a file

### Scalability

The scrape is designed to be as site-agnostic as possible. Adding a new source
to scrape is a simple one-line change: just put its URL in the
[list of sites to scrape](https://github.com/AI-Governance-Safety-Canada/content-scraping/blob/960b8172dbfb5f9ba1b40d44c92370adf37cab5f/scraper/events/sources.py).
Generally speaking, no other changes are necessary.

### Maintainability

The system includes comprehensive error handling and logging to help diagnose
and debug issues.
[It automatically retries certain errors](https://github.com/AI-Governance-Safety-Canada/content-scraping/blob/cf4161d6fd18b2de9539687d6a4b419e748dcb72/scraper/common/api/http.py)
to accommodate temporary failures. If the error persists, it logs the problem
and continues on so the rest of the scrape can complete.

The output of each run is saved locally and can also be
[published to a Google Spreadsheet](https://github.com/AI-Governance-Safety-Canada/content-scraping/blob/cf4161d6fd18b2de9539687d6a4b419e748dcb72/scraper/common/exporters/google_sheets.py).
This allows other volunteers to easily review the events for correctness and
relevance. From there, another system pushes the approved events to Airtable for
public display.

I set up a
[GitHub Actions workflow](https://github.com/AI-Governance-Safety-Canada/content-scraping/blob/cf4161d6fd18b2de9539687d6a4b419e748dcb72/.github/workflows/scrape_and_publish.yml)
to make running the scraper as hands-off as possible. It's configured to run on
a schedule and also has a manual trigger when someone wants to run it on
particular sites. The output and logs are saved for review in case anything goes
wrong.

### Extendability

I designed the system to be modular and easy to extend. The core scraping logic
is isolated from event-specific code, allowing new data types like publications
or job postings to be added in the future. Common utilities for HTML cleaning
and API interaction are
[organized into self-contained modules](https://github.com/AI-Governance-Safety-Canada/content-scraping/tree/cf4161d6fd18b2de9539687d6a4b419e748dcb72/scraper/common),
promoting code reuse and maintainability.

### Affordability

The scraper is very cheap to run. It works well with GPT-4o mini, which was
OpenAI's most economincal model at the time. Before passing each page to the
LLM,
[I strip out irrelevant content](https://github.com/AI-Governance-Safety-Canada/content-scraping/blob/cf4161d6fd18b2de9539687d6a4b419e748dcb72/scraper/common/text_processors/html.py)
such as the `<head>` and `<script>` elements. On average, this cuts the content
by about half, allowing the page to fit within the model's context while also
saving time and money. A full run consisting of roughly 20 sites, 200 pages and
200 events, costs about $0.25.

## Conclusion

The automated system delivered on all of its original goals and was well
received by the AIGS team. It's been running reliably for months now, and I
expect it will continue to save the team a lot of time. In addition, I hope it
will promote community engagement by making it easier for people to find
relevant events.

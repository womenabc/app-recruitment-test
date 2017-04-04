# Skyscanner App Recruitment test

Thanks for taking the time to do our app coding test. The challenge has two parts:

1) a [task](#task) to create a basic flight search UI and necessary network component that speaks to our 'live pricing' API

2) some [follow-up questions](./FOLLOW-UP.md)

----

Feel free to spend as much or as little time as you'd like, as long as the following have been met:

* Your implementation works as described in the [task](#task), retrieving results from [our API](#our-api).

* Your solution looks like the provided [design](#design).

----

**NB:** To get an API key and for submitting your solution, please contact the Skyscanner hiring person or member of staff who assigned you the test.

## Task

- Use our 'live pricing' API to find **return flights from Edinburgh to London, departing next Monday and returning the following day**.

- In order to successfully call the API you can find the details in the api section below

- Use the returned data to display a page of results that matches the given design.

## Design

We've provided a [design](./designs/) for phone layout. Don't worry about tackling tablet screens.

Don't worry about implementing menu functionality or sorting/filtering/alerting - these controls can be display-only.

You can see the designs both as png and as sketch, which you can use to see the more specific details. (You can download sketch from [here](https://www.sketchapp.com/))

For the airline logos, try the favicon size per code: e.g. https://logos.skyscnr.com/images/airlines/favicon/EZ.png

## Client implementation

Feel free to choose what technology or 3rd party libraries you use during the implementation.

The iOS or Android project that you create should be put into the app folder.

## API implementation

You will need to call a real Skyscanner API for this task.

The underlying Skyscanner [API documentation is available here](https://skyscanner.github.io/slate/#flights-live-prices) and a [test harness is provided](http://business.skyscanner.net/portal/en-GB/Documentation/FlightsLivePricingQuickStart) for you to try queries out.

You can use the Skyscanner `sky` location schema, and the `EDI-sky` and `LOND-sky` placenames in your query.

The API will return collections of different items:

* **Itineraries** - These are the container for your trips, tying together **Legs**, and **prices**. Prices are offered by an **agent** - an airline or travel agent.

* **Legs** - These are journeys (outbound, return) with **duration**, and **carriers**<sup>[1](#footnote1)</sup>. These contain one or more **Segments** and **stops**.

* **Segments** - Individual flight information with directionality.

A good structure to represent trip options would be hierarchical:

```
Itineraries
  Legs
    Segments
```

Your key will be rate-limited to ~5 queries per minute.

## Submission Guidelines

* Please submit your program by sending a zip file to your Skyscanner contact.

* The zip file should be named {yourname}.zip, and should itself contain the app-recruitment-test project folder with your submission.

* The zip file should contain the [FOLLOW-UP.md](./FOLLOW-UP.md) file with answers to the follow-up questions.

* Please let your Skyscanner contact know when you've uploaded your solution.

----

<a name="footnote1">[1]</a>: If there are multiple carriers provided, please use the first carrier

Inspiration for the test format taken with ❤️ from [JustEat's recruitment test](https://github.com/justeat/JustEat.RecruitmentTest).

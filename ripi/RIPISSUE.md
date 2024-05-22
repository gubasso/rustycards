# RIPISSUE

<!-- toc -->

- [ ] icp rust docs tutorial

- https://crates.io/crates/crablit

- anki-cli: space repetition study
  - cli active recall spaced repetition
  - https://roshelinarush.com/active-recall-vs-spaced-repetition/
  - https://en.wikipedia.org/wiki/Spaced_repetition
  - https://www.pnas.org/doi/10.1073/pnas.1815156116

- each card:
  - has tags to it (or categories)
  - notes and observations
  - list types of flashcards before implement... define which I will implement

## Drafts

- each user pays the rent for its own data

- rustycards backend at solana
- interfaces: web-app
- data:
  - user info
  - decks
  - cards (in each deck)
- to use a deck:
  - user has to pay
    - for each car revised
    - if gets a good score -> receives a cashback
    - if I own the deck: I pay nothing
  - % to the app developer

## Pages

- home: landing page
- deck store
- user page (decks dashboard?)
- decks/tags (all) dashboard
  - list of decks
  - list of all tags
  - each deck:
    - total cards
    - pending cards
  - calheatmap for measuring activity
    - n of reviewed tasks
    - n of scheduled tasks (future data in gray tones, different colors)
  - daily average (n of tasks)
  - days learned (n of days studyed)
  - longest streak
  - current streak
- deck page:
  - total cards
  - pending review
  - tags
  - button: "study now"
    - opens the next card
- card page:
  - open field
  - button: "Show answer"
  - shows de closed field

## Elements

- queue
  - formed by tasks
  - each task will be formed by a card
- tags (crud)
- decks (crud)
  - a set of cards
  - a queue of tasks
  - decks can have sub-decks
- cards (crud)
  - behaviour
    - each card can have 1 or N tasks
    - a basic and reversed card will have 2 tasks
    - a cloze card will have the amount of tasks defined by the amount of clozed fields (c1, c2, etc...) in the large text
  - form fields:
    - can receive text and images
  - evaluate / grade:
    - basic:
      - again / good / easy
  - types?
    - basic:
      - basic form fields: front / back
        - front: "question 1?"
        - back: "Answer..."
    - basic and reversed
      - same as `basic`
      - but at one time, the "front" will appear for you to guess the "back"
      - at the other time, the "back" will appear so you will have to guess the "front"
    - cloze
      - basic form fields:
        - text
        - extra
      - large text and you mark pieces of text to be "closed"
      - when card appears, it will hidde the "closed" text. This "closed" text will appear when you click "Show answer"
      - example:
        - "This is the large text that I have to {{c1::memorize pieces}} of it."
      - can mark multiple texts as 'c1' and they will appear closed in the same task
      - can have multiple closed texts in the same large text
      - each closed text will act as a differente card (if there is a c1, c2, etc... each will appear closed once for the same card)
    - image occlusion
      - blocks peaces of an image

## Improvements

- timer method helps go through all cards faster
- timer
  - general study session
  - shows alert when timer is ending
  - for each card/task
    - when timer ends, gives 10sec to the user select the card evaluation
      - if user doesn't select
        - auto shows the answer
        - will give more 20s
          - if idle: it will auto select "again"/"hard" evaluation to SBQ
  - give the user option to change the timer settings (general and for each card)

## Done

- [x] [[watchsolanavideos-issue]]

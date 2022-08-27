# Drop Zone
Diff technical interview question.

## 👋 Candidate instructions 

### Option

- [ ] Option A
- [x] Option B

### Technologies used 

- Vuejs
- SCSS/CSS

### Installation

To install the dependencies, run the following command at the root level of the project:

```bash
npm install
```

To run the application, run the following command at the root level of the project:

```bash
npm run dev
```

### Overview

- `src/main.js`: The entry point of the application, where you create and moont the app + import the dependencies like stylesheet and scripts.

- `src/assets` you'll find the background images and a css stylesheet, with a minimal reset.

- `src/components` you'll find the `Countdown.vue`, where all the logic and style for that component.

- `src/App.vue`, is the main `view` of the application. Where we import the `Countdown.vue` component & integrated the laytout of the landing.

## Instructions
* There are no time restrictions.
* The exercise is open-book, feel free to use any resource available to you.
* Use the frameworks of your choice to build a solution that meets the requirements (example: jQuery, Bootstrap, Vue, etc).
   * If compilation is required to run the solution, include instructions.

You can work on this solution in one of two ways: by forking this repository, or sending your zip file.

### Forking
1. Fork the repository to your own account.
2. Build a web page that follows the technical requirements below.
3. Send a link to your repository so it can be cloned.

### Zip
1. Clone the repository to your local environment.
2. Build a web page that follows the technical requirements below.
3. Send a zip file of the finished solution.

## Requirements
### Option A
1. The solution matches the mock ups.
1. The countdown timer decrements in real time.
1. The timer begins at 13 days, 8 hours, 12 mins and 5 seconds when the page loads.

### Option B
1. The solution matches the mock ups.
1. The countdown timer decrements in real time.
1. The timer counts down to midnight to a configurable date.
   1. Declare a `date` variable that can take a date of format `MM/DD/YYYY`.

## Mockups
https://www.figma.com/file/OGZEMBBrVIM3n2CdBYsdEK/Drop-Zone?node-id=0%3A1
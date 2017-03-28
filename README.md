# Easy Box Model (EBM) 3.0.0 - Gulp Optimized

## Getting started

- Install the framework of your preference, `cd` into the `assets` folder (it may be the `public` in most of the cases)
- `git clone https://github.com/EasyBoxModel/EBM.git .`
- `npm install`
- `gulp` or `gulp watch` to watch for changes
- Open the `gulpfile.js` and change `PUBLIC` to match the public assets __destination__ folder and `SRC_FOLDER` to match the source folder
- You may use these handy terminal commands:

```bash
export dest_path="public"
export resources_path="resources/assets";
export resources_esc_path="resources\/assets";
sed -i '' "s/PUBLIC/$dest_path/g" "gulpfile.js"
sed -i '' "s/SRC_FOLDER/$resources_esc_path/g" "gulpfile.js"
sed -i '' "s/SRC_FOLDER/$resources_esc_path/g" "$resources_path/sass/global.scss"
sed -i '' "s/SRC_FOLDER/$resources_esc_path/g" "$resources_path/sass/_ebm-imports-reference.scss"
```

## Usage

EBM is an MVC-CSS/JS frontend framework. It may sound verbose, but it is designed to follow modern frameworks MVC structure.

### CSS

Let's assume that your FW has an `Users` module, a `UserController` and a `profileAction()` that renders a view. For this case, the `sass` folder may have the following structure:

```
sass
    users
        user
            profile.scss
```

The `profile.scss` file may import the `global.scss` which manages the shared styles and may import specific EBM control, elements or modules so only the _profile_ view uses them:

```sass
@charset "UTF-8";

// Import the global styles and mixins for every template
@import "./SRC_FOLDER/sass/global";

// Module Controller group specific EBM Imports
@import "./SRC_FOLDER/scss/EBM/elements/ebm-custom-radio-checkbox";

// Additional classes
.profile-class {
  // ...
}
```

In order to have a `css/users/user/profile.css` file available for your HTML `link` tags, just do a `gulp` or `gulp-styles`. Choose `gulp-watch` instead to watch for changes.

### JS

The same goes for javascript files except for the `action` folder which has always a `main.js` file:

```
js
    src
        module
            controller
                action
                    main.js
```

The `main.js` has the `require()` code that uses `node_modules` packages and your view or component code:

```js
let Vue = require('vue');

let Component = Vue.extend({
  template: '#name',
  data(){
    return {}
  },
  ready(){},
  methods: {}
});

Vue.component('name', Component);
```

The code above will compile into a `js/build/module/controller/action.js` file minified in production and development enviroments.

## Description

The EBM is a structured set of frontend libraries and tools and a workflow proposal on how to use them to drastically increase web development productivity.

### Thoughts about time

After having worked on at least 20 web projects throughout 18 months, we discovered that __time tracking does not objectively measure productivity__, instead, we prefer talking about __time efficiency__, where the ammount of time taken to complete a project in the stages of development, Q&A and production can be decreased if each individual inside the development team uses __productivity resources__.

### Productivity resources

So, if time tracking does not objectively measure development productivity: __How can we make sure that at least, we are taking less time on completing tasks and completing them well?__


### Taking less time on completing tasks

__Habits__. Development habits are systematic steps that individuals take to complete the given tasks.

Even the simplest tasks, add up to the overall development time of the project

Here is a list of how the EBM proposes to work on these habits:

- Naming conventions in files, selectors and elements
- Text editor shortcuts and tools
- Browser shortcuts and tools
- Computer shortcuts and tools
- Size units value references
- Command line aliases
- Troubleshooting techniques
- Aknowledgement of the available resources
- Health and comfort considerations


### Less time, but without compromising the product quality

Can we get a balance between time and quality?

Can we accomplish it on large teams?

What does quality mean?

- Accessibility
- Performance
- Readibility
- Compatibility
- Scalability
- Functionality

## EBM aims to:

- Create __workflow consistency__ for frontend development teams
- Define a standard set of development tools to __ensure product quality__
- Help developers on building their __time efficiency habits__
- Help on the __development team communication__ process by specifying naming conventions and project structure
- Document and __automate__ processes
- Output light CSS files for its use in CMS's and __scalable web applications__
- Help frontend development teams to __think in the Sass way__

### EBM expected outputs

- Satisfy the customer through __early and continuous delivery of valuable software__
- __Welcome changing requirements__, even late in development. Agile processes harness change for the customer’s competitive advantage
- __Deliver working software frequently__, from a couple of weeks to a couple of months, with a preference to the shorter timescale
- __Working software is the primary measure of progress__
- __Sustainable development__. The sponsors, developers, and users should be able to maintain a constant pace indefinitely
- Continuous __attention to technical excellence and good design__ enhances agility
- __Simplicity__
- Self-organizing teams
- At regular intervals, the team reflects on how to become more effective, then tunes and adjusts its behavior accordingly

# wordwrap-protractor-jasmine2-html-reporter

[![npm version](https://badge.fury.io/js/wordwrap-protractor-jasmine2-html-reporter.svg)](http://badge.fury.io/js/wordwrap-protractor-jasmine2-html-reporter)

HTML reporter for Jasmine2 and Protractor that will include screenshots of each test if you want. This work is inspired by:

- [Protractor Jasmine 2 Screenshot Reporter](https://github.com/mlison/protractor-jasmine2-screenshot-reporter) from [@mslison](https://github.com/mlison)
- [Jasmine Reporters](https://github.com/larrymyers/jasmine-reporters) from [@larrymyers](https://github.com/larrymyers)

## Usage

The `wordwrap-protractor-jasmine2-html-reporter` is available via npm:

`$ npm install wordwrap-protractor-jasmine2-html-reporter --save-dev`

In your Protractor configuration file, register protractor-jasmine2-html-reporter in jasmine:

```
var Jasmine2HtmlReporter = require('wordwrap-protractor-jasmine2-html-reporter');

exports.config = {
   // ...
   onPrepare: function() {
      jasmine.getEnv().addReporter(
        new Jasmine2HtmlReporter({
          savePath: 'target/screenshots'
        })
      );
   }
}
```

## Options

### Destination folder

Output directory for created files. All screenshots and reports will be stored here.

If the directory doesn't exist, it will be created automatically or otherwise cleaned before running the test suite.

```
jasmine.getEnv().addReporter(new Jasmine2HtmlReporter({
   savePath: './test/reports/'
}));
```

Default folder: `./`

### Screenshots folder (optional)

By default the screenshots are stored in a folder inside the default path

If the directory doesn't exist, it will be created automatically or otherwise cleaned before running the test suite.

```
jasmine.getEnv().addReporter(new Jasmine2HtmlReporter({
   savePath: './test/reports/',
   screenshotsFolder: 'images'
}));
```

Default folder: `screenshots`

### Take screenshots (optional)

When this option is enabled, reporter will create screenshots for specs.

```
jasmine.getEnv().addReporter(new Jasmine2HtmlReporter({
   takeScreenshots: false
}));
```

Default is `true`

### Take screenshots only on failure (optional) - (NEW)

This option allows you to choose if create screenshots always or only when failures. If you disable screenshots, obviously this option will not be taken into account.

```
jasmine.getEnv().addReporter(new Jasmine2HtmlReporter({
   takeScreenshots: true,
   takeScreenshotsOnlyOnFailures: true
}));
```

Default is `false` (So screenshots are always generated)

### FixedScreenshotName (optional)

Choose between random names and fixed ones.

```
jasmine.getEnv().addReporter(new Jasmine2HtmlReporter({
   savePath: './test/reports/',
   fixedScreenshotName: true
}));
```

Default is `false`

### FilePrefix (optional)

Filename for html report.

```
jasmine.getEnv().addReporter(new Jasmine2HtmlReporter({
   savePath: './test/reports/',
   filePrefix: 'index'
}));
```

Default is `htmlReport.html`

### Consolidate and ConsolidateAll (optional)

This option allow you to create diferent HTML for each test suite.

```
jasmine.getEnv().addReporter(new Jasmine2HtmlReporter({
   consolidate: true,
   consolidateAll: true
}));
```

Default is `false`

### CleanDestination (optional)

This option, if false, will not delete the reports or screenshots before each test run.

```
jasmine.getEnv().addReporter(new Jasmine2HtmlReporter({
   savePath: './test/reports/',
   cleanDestination: false
}));
```

Default is `true`

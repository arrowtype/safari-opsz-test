# Safari Optical Size Error Report

GitHub repo for a WebKit/Safari Error Report.

See https://arrowtype.github.io/safari-opsz-test for a live browser test.

In Safari Technology Preview (Release 173 (Safari 17.0, WebKit 18616.1.20.2)):
- In a variable font with an Optical Size (`opsz`) axis and Weight (`wght`) axis
- If the `wght` and `opsz` axes are at their defaults (often, `wght=400` and `opsz` somewhere between about `8` and `20`)

...The `opsz` that gets *rendered* is the font’s maximum `opsz`. 

This is tested in Roboto Flex, Roboto Serif, Newsreader, Fraunces, and other variable fonts with `wght` & `opsz` axes.

Another simple way to test this is to load such font into [Wakamai Fondue](https://wakamaifondue.com/beta/). It has type testers that are set to the font’s defaults.

Please note: in the current main Safari, there are other `opsz` inconsistencies. For example, if you go to a font’s max `opsz`, the rendered font weight will suddenly be the min `wght`. So, please test for that while fixing this, and don’t e.g. simply revert changes to opsz handling (not that I think you would, but there have been problems here for awhile, so I want to suggest care in addressing it).

## Screenshots

![Safari Optical Size issue, Fraunces](images/safari-issue-opsz-fraunces.png)
![Safari Optical Size issue, Roboto Flex](images/safari-issue-opsz-robotoflex.png)
![Safari Optical Size issue, Newsreader](images/safari-issue-opsz-newsreader.png)

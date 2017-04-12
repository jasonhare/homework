// Your recommended changes go here
# My Approach

I want to give a overview into the process I use when I'm auditing a site for accessibility. This is by no means an exhaustive audit , but instead a set of quick checks that I use to highlight any big problem areas. 

## Caveat on this Analysis

Note- this type of analysis is retro fitting and called accomodation or equivalent. I do not advocate this type of testing. Rather I would like to see accessibility as something done earlier in the process. Accessibility is a subset of usability. That being said here are some of the main things I look for:

* Does the tab order make sense and can I reach all controls on the page?
* Is there a clear focus indicator for interactive controls? Yes, using Chrome.
* Are there any offscreen elements which should not be focusable? No- everything was on one screen.
* Can I traverse the page with a screen reader without getting stuck? I was able to using VoiceOver
* Is there appropriate alt text on images? Yes
* Do custom controls work with a screen reader? Yes
* Is the user alerted to new content added to the page? Not always
* Are there appropriate headings? Mostly- some missing
* What about landmark elements? Yes
* Is text high contrast enough to be legible? Yes

## My Tool Kit (Partial)

Chrome aXe extension: https://goo.gl/67Bm24
Chrome accessibility devtools extension: https://goo.gl/DvAxi2
aXe-core: https://github.com/dequelabs/axe-core

# Visual to the UI (CSS, visual elements)

## Home Page

### Header
A header element or banner landmark is present. This is good. Headers identify page introduction or navigation. They typically surrounds the site or page name, logo, top navigation, or other header content. Headers facilitate page semantics and navigation.

#### Best Practices
Ensure the header surrounds and defines page header content. 

#### Standards and Guidelines References WCAG
1.3.1 Info and Relationships (Level A)
2.4.1 Bypass Blocks (Level A)

### Tabs

Landmark "skip navigation" was there but I could not tab through the homepage.

Individuals and Families is a redundant link. Adjacent links go to the same URL. There are two addisional redundant links on the home page.

#### Best Practices
When adjacent links go to the same location (such as a linked product image and an adjacent linked product name that go to the same product page) this results in additional navigation and repetition for keyboard and screen reader users.

#### How I would Fix It
If possible, combine the redundant links into one link and remove any redundant text or alternative text (for example, if a product image and product name are in the same link, the image can usually be given alt="").

#### Standards and Guidelines References WCAG
2.4.4 Link Purpose (In Context) (Level A)

### Homepage ZipCode Fieldset Missing Legend
Fieldset missing legend

#### Best Practices
A fieldset legend presents a description of the form elements within a fieldset and is especially useful to screen reader users. A legend should be provided when a higher level description is necessary for groups of check boxes, radio buttons, or other form controls.

#### How I would Fix It
If a higher level description is necessary for the user to understand the function or purpose of the controls within the fieldset, provide this description within the <legend>. If this description or grouping is not necessary, the fieldset should probably be removed. Note that the legend is repeated to screen reader users for each form control within the fieldset.

#### Standards and Guidelines References WCAG and Section 508
Section 508 (n)
1.1.1 Non-text Content (Level A)
1.3.1 Info and Relationships (Level A)
2.4.6 Headings and Labels (Level AA)
3.3.2 Labels or Instructions (Level A)

# Technical changes: HTML, CSS, Javascript, ARIA attributes

All ARIA elements are correctly implemented. There were only two errors on the home page and subsequent pages. Neither of these errors had anything to do with ARIA, they were heading and field labels missing.

# Content

Users were drawn to new content with high contrasting CSS elements. Tabbing through the site was an issue.

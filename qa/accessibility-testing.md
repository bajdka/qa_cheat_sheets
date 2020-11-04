## Accessibility Cheat Sheet

### Checklist
https://webaim.org/standards/wcag/checklist

### Courses 
https://github.com/mgifford/a11y-courses

### Podcasts
https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g

### ARIA Authoring Practises
https://www.w3.org/TR/wai-aria-practices/

### Principle 1 – Perceivable

**1. All non-text content that is presented to the user has a text alternative that serves the equivalent purpose.**
* for images, use the alt attribute
* for audio and video elements, provide text transcripts.
* for user interface elements, use labels.

**2. Provide alternatives for time-based media.**
* sign language as part of a video file
* alternative audio for video files
* video file with sign language as alternative for audio files

**3. Create content that can be presented in different ways (for example simpler layout) without losing information or structure.**
* Document should be readable and understandable without any CSS. 
* Sensory characteristics such as shape, size, visual location, orientation, or sound should not be the only way of conveying important information.

**4. Make it easier for users to see and hear content including separating foreground from background.**
* Color is not used as the only visual means of conveying information, indicating an action, prompting a response, or distinguishing a visual element.
* Contrast ratio of text to background should be at least 4.5:1, preferably 7:1. [Find contract ratio](https://contrast-ratio.com/)
* Text should be easily resizable up to 200%
* Use actual text instead of images of text
* Control over audio media should be provided

### Operability

**1. Make all functionality available from a keyboard.**
* Ensure all functional elements have a clear focus state ([JS hint](https://www.w3.org/TR/2014/NOTE-WCAG20-TECHS-20140916/SCR29))
* Avoid keyboard traps

**2. Provide users enough time to read and use content.**
* Users can turn off the time limiit
* Users can adjust time limit to at least 10 times the length of the default setting
* Users is warned before time expires and given at least 20 seconds to extend the time limit with a simple action

**3. Do not design content in a way that is known to cause seizures.**
* Flashing light should not occur more than three times per second.
* (Photosensitive Epilepsy Analysis Tool)[http://trace.umd.edu/peat]
* (Online Flash Test)[https://www.onlineflashtest.com/]

**4. Provide ways to help users navigate, find content, and determine where they are.**
* Provide a link for users to skip to the page's main content.
* Titles should be meaningful.
* Link purpose can be determined from link text.
* Provide more than one way to locate a web page. (site map, navigation, search)
* Provide information about the current location. (breadcrumbs, site map, highlighting the current location in navigation, using the `<link rel="index | next | prev | contents">` tag to specify the current page's relationship to other pages)
* Pages have titles

### Unserstadability

**1. Make text content readable and understandable.**
* Specify the language(s) of the page. (`lang="en"`)
* Provide meanings of unusual words and pronunciations of difficult words. 
* Make content available at a lower secondary education reading level.
* A mechanism for identifying the expanded form or meaning of abbreviations is available.



**2. Make Web pages appear and operate in predictable ways.**
* Consistent navigation.
* Consistent identification. (terminology, repeatable elements)
* No unprovoked changes of context (things like redirects, popups and other similar interactions should be communicated clearly beforehand.)

**3. Help users avoid and correct mistakes.**
* Provide labels and instructions.
* Error messages in simple language.
* Error prevention.

**4. Maximize compatibility with current and future user agents, including assistive technologies.**


### Robustness

**1. Maximize compatibility with current and future user agents, including assistive technologies.**
* Valid doctype
* Valid character encoding specified
* Complete start and end tags
* No duplicate attributes, for examples IDs




#### Literature
* https://bitsofco.de/the-accessibility-cheatsheet/
* https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0
* https://usabilitygeek.com/10-free-screen-reader-blind-visually-impaired-users/
* https://material.io/design/usability/accessibility.html
* https://24ways.org/2017/wcag-for-people-who-havent-read-them
* https://design.google/library/designers-guide-accessibility-research
* http://www.widzialni.eu/container/podrecznik6-www.pdf?fbclid=IwAR3qyPGV7xmg9kSiWepM8XiOg1i2TpL4ysyMg2L97XH1oolCAMKzRILuMUM
* http://niepelnosprawni.pl/ledge/x/302849



#### Tools
* https://www.deque.com/axe/
* https://addons.mozilla.org/en-US/firefox/addon/wcag-contrast-checker
* https://chrome.google.com/webstore/detail/html5-outliner
* http://www.fdc.org.pl/gallery/Narz%C4%99dzia_do_badania_i_tworzenia_dost%C4%99pnych_tre%C5%9Bci.pdf

# PurpleLabs QA
PRPL Labs was born from the need to engage with businesses and consumers at the forefront of technology.

## Issue
PRPL labs Google Glass Project link to view the website redirects users to a dead end.
<img src="http://donpage.github.io/images/PRPL-issue.gif"/>

## Solving
Solving the issue is simple, the only thing I had to do is change the href attribute of the anchor tag that held the false link:

#### Problem:

`<a href="http://purplerockscissors.com/labs/glass/" target="_blank" class="ext-link white-button">Visit the Site</a>`

#### Correction:

`<a href="http://prpllabs.com/glass/" target="_blank" class="ext-link white-button">Visit the Site</a>` OR `<a href="/glass/" target="_blank" class="ext-link white-button">Visit the Site</a>`

<img src="http://donpage.github.io/images/PRPL-fix.gif"/>


## How this problem happened:
PRPL Labs is still in it's infancy phase, while still being apart of the main agency (Purple, Rock Scissors), PRPL Labs are making their own move away from the company and becoming it's own thing. In doing so they changed domains and in turn caused this small problem with redirecting users to the right location.

## Solving ahead of time:
As a developer myself I'm always thinking about the next step for the project. I must be able to account for working locally, deployment, and any major change in infrastructure. While changing domains was a major change that was done successfully, accounting for the changes in redirection of links slipped thru the cracks. One simple solution to this would to *NOT* link directly to the website since it's in the subdomain of the current URL the user is accessing the site from, for example:

### If the current URL is http://prpllabs.com

#### Bad:

`<a href="http://prpllabs.com/glass/" target="_blank" class="ext-link white-button">Visit the Site</a>`

#### Good:

`<a href="/glass/" target="_blank" class="ext-link white-button">Visit the Site</a>`


---

### If the current URL is http://purplerockscissors.com

#### Bad:

`<a href="http://purplerockscissors.com/about/">About</a>`

#### Good:

 `<a href="/about/">About</a>`

---

#### Following the rules above will ensure that this issue doesn't happen again when changing domains.
<img src="http://i.imgur.com/3nuaixP.gif" />


Best wishes, DonPage | http://donpage.github.io




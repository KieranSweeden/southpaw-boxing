# Southpaw Boxing Club Testing

To go back to the README file, [click here](README.md).

## Index

1. [Validation Testing](#Validation-Testing)

   - [HTML Validator](#HTML-Validator)
   - [CSS Validator](#CSS-Validator)

2. [Performance Testing](#Performance-Testing)

   - [Lighthouse Desktop](#Lighthouse-Desktop)
   - [Lighthouse Mobile](#Lighthouse-Mobile)

3. [User Stories Testing](#User-Stories-Testing)

4. [Manual Testing](#Manual-Testing)

5. [Bugs](#Bugs)

   - [Fixed](#Fixed)
   - [Remaining](#Remaining)

6. [Responsive Design Testing](#Responsive-Design-Testing)

   - [Hardware Used](#Hardware-Used)

## Validation Testing

### HTML Validator

The HTML validator results from the [W3C Markup Validation Service](https://validator.w3.org/) for each page can be found below:

<details>
   <summary>index.html</summary>

![Index page html validator results](/assets/images/readme/validator/html-validator-index.png)

</details>

<details>
   <summary>boxing-guide.html</summary>

![Index page html validator results](/assets/images/readme/validator/html-validator-boxing-guide.png)

</details>

<details>
   <summary>sessions.html</summary>

![Index page html validator results](/assets/images/readme/validator/html-validator-sessions.png)

</details>

<details>
   <summary>contact.html</summary>

![Index page html validator results](/assets/images/readme/validator/html-validator-contact.png)

</details>

<details>
   <summary>form-success.html</summary>

![Index page html validator results](/assets/images/readme/validator/html-validator-form-success.png)

</details>

### CSS Validator

The CSS validator results from the [W3C CSS Validation Service](https://jigsaw.w3.org/css-validator/) for style.css can be found below:

<details>
   <summary>style.css</summary>

![Style.css validator results](/assets/images/readme/validator/css-validator-results.jpg)

</details>

## Performance Testing

### Lighthouse Desktop

[Google Lighthouse](https://developers.google.com/web/tools/lighthouse) was used to test the performance of the website for desktop. Google Chrome encouraged that performance testing should be done in incognito mode, so that was done prior to investigating performance. You can view a report of what took place to improve performance for each page below:

<details>
<summary>index.html</summary>

![Index page performance results](/assets/images/readme/performance/index.html-before.jpg)

The results for the index.html file on desktop came back positive, with few adjustments needed to improve performance & accessibility.

Regarding performance, the only warning the report provided was that the logo graphic didn't have an explicitly set width & height.

![Warnings for performance in index.html](/assets/images/readme/performance/warning-index-performance.jpg)

After looking at the best practises provided by web.dev [here](https://web.dev/optimize-cls/?utm_source=lighthouse&utm_medium=devtools#images-without-dimensions), it suggests using the aspect-ratio property. Although this method works and is [supported by most of the major browsers](https://caniuse.com/mdn-css_properties_aspect-ratio), it's not deemed as valid CSS at the time of writing this by the W3C CSS validation service. Thus resulting in an error when using their validator. Because of this, I decided to omit this particular warning, especially when considering it doesn't have a major influence over the page.

Regarding accessibility, Lighthouse provided two warnings shown below:

![Warnings for accessibility in index.html](/assets/images/readme/performance/warning-index-accessibility.jpg)

The first warning stated that a lack of headers made the page inaccessible. I was able to tackle this warning by looking at [this Stack Overflow post](https://stackoverflow.com/questions/665037/replacing-h1-text-with-a-logo-image-best-method-for-seo-and-accessibility). The answer provided by Rahul (later edited by Henrique) was a sufficient fix for this warning.

The secondwarning stated that the social media links didn't contain any respective discernible names. I was able to tackle this warning by applying an aria-label attribute to each social media link.

These fixes provided me with an optimal score for the index.html page as shown below:

![Index page results after fixes](/assets/images/readme/performance/index.html-after.jpg)

</details>

<details>
<summary>boxing-guide.html</summary>

![Boxing guide page results before fixes](/assets/images/readme/performance/boxing-guide.html-before.jpg)

The results given back from Lighthouse regarding the boxing-guide.html file was good, however improvements could be made throughout especially in performance and accessibility.

Lighthouse provided an opportunity in improving performance by pre-loading a particular image. The image itself isn't large, being a total size of 68.KB which made this suggestion peculiar. Regardless I followed the advice given within [this web.dev article](https://web.dev/optimize-lcp/?utm_source=lighthouse&utm_medium=devtools#preload-important-resources), which suggests adding preload functionality to critical assets which made sense given this image is present throughout the entirety of the page.

Still on performance, the first warning was the boxing-guide.html file does not use passive listeners to improve scroll performance. Given this is a JavaScript related fault and is out of my depth and of the scope of this project, I've decided to leave it be. When having a better understanding of event listeners in JavaScript, this is something I could foreseeably come back to and fix.

The last warning in performance was certain images not having explicitly set width and heights, as shown below:

![Images not having set width & height's in boxing-guide.html](/assets/images/readme/performance/boxing-guide.html-img-width-height.jpg)

This was easily fixed when following the [web.dev](https://web.dev/optimize-cls/?utm_source=lighthouse&utm_medium=devtools#images-without-dimensions) article, which suggests adding native html width & height values to the img element to provide the browser with an aspect ratio.

Regarding accessibility Lighthouse reported that many buttons (particularly the header dropdown buttons) throughout didn't contain an accessible name as shown below:

![Buttons do not have accessible names in boxing-guide.html](/assets/images/readme/performance/boxing-guide.html-semantics-buttons.jpg)

This was swfitly fixed by adding aria-label attributes to each button that opens the boxing guide navigation menu.

Lastly the social media links within the footer needed accessible names also, similarly to the warnings given for index.html.

Moving to SEO, Lighthouse reported a link that didn't contain any descriptive text as shown below:

![Link does not have descriptive text in boxing-guide.html](/assets/images/readme/performance/boxing-guide.html-semantics-buttons.jpg)

It reports that "here" is not descriptive enough for search engines to understand the link's purpose. Therefore I included more of the paragraph into the link text, to give it a more in-depth description which is of more use to screen reader users and search engines.

These fixes provided me with a respectable overall score shown below:

![Boxing guide page results after fixes](/assets/images/readme/performance/boxing-guide.html-after.jpg)

</details>

<details>
<summary>sessions.html</summary>

Prior to generating a Lighthouse report for the sessions page, I added aria-labels to the social media links within the footer as I expected them to be reported given reports regarding previous pages.

After the inclusion of aria-labels, I generated a report and was pleasantly surpised to see an optimal report as shown below:

![Session page results](/assets/images/readme/performance/sessions.html-report.jpg)

</details>

<details>
<summary>contact.html</summary>

Similarly to the sessions.html page, the social media links were provided with aria-labels within the contact.html file. The report also provided an optimal score as shown below:

![Contact page results](/assets/images/readme/performance/contact.html-report.jpg)

</details>

<details>
<summary>form-success.html</summary>

Despite adding aria-labels, there were additional issues to resolve regarding the form-success.html file. The report for the file is shown below:

![Form success page results before fixes](/assets/images/readme/performance/form-success.html-before.jpg)

The one warning present within the SEO section of the Lighthouse report, states that it's best practise to include for a meta description for various reasons as shown below:

![Lack of meta description within the form success page](/assets/images/readme/performance/form-success.html-meta.jpg)

This problem was quickly fixed in including a suitable meta description for the page. After this fix, Lighthouse provided an optimal report as shown below:

![Form success page results after meta description fix](/assets/images/readme/performance/form-success.html-after.jpg)

</details>

### Lighthouse Mobile

<details>
<summary>boxing-guide.html</summary>

Boxing-guide.html was the stand out in lack of performance, mostly due to render-blocking resources which after investigating, seem to be out of the scope of this project. The results for boxing-guide.html can be seen below:

![boxing-guide.html mobile testing results before fixes](/assets/images/readme/performance/mobile-boxing-guide.html-before.jpg)

Despite a large portion of the problems deriving from render-blocking resources, other performance improvement opportunities have been suggested, as shown below:

![boxing-guide.html mobile performance improvement opportunities](/assets/images/readme/performance/mobile-boxing-guide.html-opportunities.jpg)

After investigating, removing un-used CSS would require additional tools and applications which would fall out of the scope of this project.

Although removing spaces in the style.css makes sense to improve performance, this project is being accessed, and therefore the formatting needs to be readable for the individual marking this project, meaning this cannot be done either.

What can be done, is making sure the images are properly sized and optimized for mobile. Lighthouse's suggestions are given below:

![boxing-guide.html images that should be properly sized for mobile](/assets/images/readme/performance/mobile-boxing-guide.html-images.jpg)

This was promptly fixed by creating two new files that were smaller in size and using the srcset attribute within an img element. The idea for this came from [this Mozilla article](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images) on responsive images.

After generating a new report, the properly size images opportunity disappeared. However a new opportunity arose relating to pre-connecting to establish early connections with third parties, as shown below:

![boxing-guide.html preconnect opportunity](/assets/images/readme/performance/mobile-boxing-guide.html-preconnect.jpg)

After following [this web.dev article](https://web.dev/uses-rel-preconnect/?utm_source=lighthouse&utm_medium=devtools) on preconnecting to required origins and adding a link in the head of the boxing-guide.html file, the performance of the site came back optimal as shown below:

</details>

<details>
<summary>Other pages</summary>

Other than Lighthouse suggesting to eliminate render-blocking resources which are out of the scope of this project, all of the other pages gave optimal results when tested for mobile devices as is shown below:

index.html results
![index.html mobile testing results](/assets/images/readme/performance/mobile-index.html.jpg)

sessions.html results
![sessions.html mobile testing results](/assets/images/readme/performance/mobile-sessions.html.jpg)

contact.html results
![contact.html mobile testing results](/assets/images/readme/performance/mobile-contact.html.jpg)

form-success.html results
![form-success.html mobile testing results](/assets/images/readme/performance/mobile-form-success.html.jpg)

</details>

## User Stories Testing

As a new visitor & potential attendee, I want to:

- Discern whether the boxing club is suitable for my current level of experience.
  - The first paragraph within the home page immediately mentions that it's official guide is for people at all boxing levels.
  - The first paragraph within the boxing guide makes it's goals clear in preparing people of all levels for their first session with Southpaw.
- Quickly observe the public sessions, deducing as to which session is most suitable for my current goal.
  - A link to the sessions is immediately visible from the home page, which'll take the user directly to the sessions page.
  - The sessions are given a paragraph respectively, briefly detailing what goes on within each one, helping the user make an educated decision as to what session suits their goals.
- Be informed as to what clothing is appropriate for the boxing sessions.
  - A link to information regarding clothing is clearly shown at the intro section of the boxing guide, which'll immediately take the user to the clothing section.

As a new visitor who is a parent of a potential attendee, I want to:

- Understand the organisation and it's sessions in detail, to discern whether it's the right fit for my child.
  - A link to information regarding boxing for juniors with Southpaw is clearly shown at the intro section of the boxing guide, which'll immediately take the parent to the information regarding juniors.
  - The junior boxing section is essentially an FAQ, that attempts to answer the most common questions that are likely to be asked by parents. This informs the parent of Southpaw's methods in teaching boxing to juniors, helping them discern whether it's the right fit for their child.
- Be informed as to what clothing my child should wear when attending boxing sessions.

  - A link to information regarding clothing is clearly shown at the intro section of the boxing guide.
  - The clothing section provides information on ideal for tops and bottoms.

As a returning visitor, I want to:

- Contact the organisation for the purpose of discussing & scheduling a private session.
  - A link to the contact page is immediately visible within the home page.
  - A link to the contact page is always visible throughout most of the pages in the nav bar at the top of the page.
  - A "Contact Us" button that takes the user to the contact page is present within the private session section of the sessions page.
  - A "Book Private" option is provided within the select input within the form.
- Quickly observe the public sessions, to investigate the sessions I have not attended thus far.
  - A link to the sessions page is immediately visible from the home page.
  - A link to the sessions page is always visible throughout most of the pages in the nav bar at the top of the page.
  - The sessions page has an aside section with days and times for each session respectively.
  - A link to see the address of the venue where the session is taking place, is visible in the aside section for each session respectively. This opens a new tab or opens Google Maps and shows the user where the venue is. This helps the user determine whether they can attend the sessions they have not attended so far.

As a visitor in general, I want to:

- Swiftly navigate to the parts of the website which are relevant to me.

  - Links to each meaningful page (Boxing Guide, Sessions & Contact) is presented clearly in the home page and nav bar.
  - Where relevant, links are integrated within paragraphs to help the user swiftly navigate to the page useful to them. For example, in the junior boxing section, there is a link to the contact form within a paragraph if the parent has any more questions.
  - There are buttons to each meaningful section of the boxing guide within the intro section.
  - When clicked, the headers within the boxing guide open a dropdown menu. Links to immediately navigate to the section relevant to the user are provided within this dropdown menu.

- Promptly discover the times and locations for each public session respectively.

  - A link to the sessions page is immediately visible to the user from the home page and in the navbar that's present throughout most of the pages.
  - Within the sessions page, the days, times and a link to the address in which the session is taking place is provided for each session respectively.

- Be able to contact the organisation for any additional questions I may have.

  - A link to the contact page is immediately visible to the user from the home page and in the navbar that's present throughout most of the pages.

- Easily find the organisations' social media links, so I can keep up to date with what's new.

  - Social media links can be found at the bottom of every page within the site. These links open a new tab, meaning the user can still continue in browsing the Southpaw site with no hassle.

## Manual Testing

The functionality of the features/elements presented below have been tested.

- Home

  - All links to their respective pages within the website work properly.
  - All links to their respective pages change colour when hovered or in focus.
  - All social media links direct the user to the respective social media site in a new tab.
  - All social media links change colour when hovered or in focus.
  - Background video changes depending on screen size.
  - Two columns are present for desktop/laptop screens and the 1st of the two disappears when the screen size is under the 1200px breakpoint.
  - The Southpaw Boxing Club logo in the 2nd column appears when the 1st column disappears

- Boxing Guide

  - The container turns from fluid to non-fluid depending on screen size.
  - When clicked, each boxing guide navigation header for each section opens it's dropdown menu when clicked.
  - When hovered, a green line appears for each boxing guide navigation header.
  - The scroll-snap is set to mandatory for larger screens and proximity for smaller screens.
  - Each link within the dropdown menu takes the user to that section as expected.
  - Each button has a hover/active state and directs the user to the specified section of the boxing guide.
  - Each button within a section opens it's respective modal containing more information.
  - Every X and close button within each modal closes it's respective modal.
  - Each link to an external site opens the link in a new tab.
  - Each link to an internal page within the website is highlighted with the lime colour.
  - Videos start immediately whilst being infinitely looped and muted.
  - Buttons disappear/appear depending on screen size.
  - The balance of text content shared by each section's main page & modal is determined by the screen size.
  - Certain pictures & videos appear/disappear depending on screen size.
  - The main footer is visible for desktop/laptop screen sizes and disappears for tablet screen sizes and below.
  - The boxing guide footer appears for mobile screens and above, until the screen reaches desktop/laptop sizes, in which it then disappears.

- Sessions

  - The container turns from fluid to non-fluid depending on screen size.
  - The flex column is set to column for mobile devices and tablets when in portrait orientation.
  - The flex column is set to row for tablets in landscape orientation and desktop/laptop devices.
  - Each link/button has a hover/focus state and directs the user the specified location.
  - Each address link opens the link in a new tab for desktops/laptops and opens Google Maps for mobile & tablet devices.
  - Images disappear for smaller screen sizes.
  - Video plays automatically whilst being infinitely looped and muted.

- Contact

  - The container turns from fluid to non-fluid depending on screen size.
  - The image appears/disappears depending on screen size.
  - The "Call Us" button has a hover/focus state & immediately prompts mobile users to call with a given number.
  - Each input within the form has a focus state, informing the user as to where they are within the form.
  - Each input has a required attribute, alerting the user when a field needs to be completed before submission.
  - The submit button has hover/focus state and directs the user to the form success page.

- Form success

  - The container turns from fluid to non-fluid depending on screen size.
  - The image appears/disappears depending on screen size.
  - Each button has a hover/focus state and directs the user to the specified location.

- Navigation Bar

  - The Southpaw logo is shown for larger screen sizes and an appreviated "S" is shown for smaller screen sizes.
  - Clicking either the graphic logo or the appreviated "S" will direct the user to the home page.
  - Hover/focus states are given to each link in the nav bar and are additionaly used to inform the user as to what page they're currently on.

- Footer
  - All social media links have a hover/focus state & direct the user to their respective social media sites in a new tab.

## Bugs

This section contains any consistent bugs that proved to be difficult during the development cycle of this project.

### Fixed

- A common occuring bug throughout the development process was dealing with Bootstrap 5 constantly making columns within rows have top, right, bottom and left margins of -12px. This was severely impacting the overall visual structure of the webpages. After investigating the issue with Dev Tools, I found the issue and resolved it by applying Bootstrap's own margin classes to the columns list of classes respectively.

### Remaining

- Unfortunately for some particular browsers, the scroll-snap functionality doesn't work particularly well despite the property being supported on most browsers. The browsers in question are Safari & Google Chrome for iOS. This was found during a UX test, where the user was using their iPad and the scroll-snap-point would snap to the top of the viewport rather than the bottom of the navigation as intended. What was unusual however, was that over a period of time the functionality would begin to work, which makes sense as the bug wasn't presented on my own devices, which probably contained cache regarding my website.

- Due to me being focused on the portrait orientation of the site when it comes to being viewed on mobile, it's meant the landscape experience of the site is poor due to various bugs which largely fall under sizing & styling. Although I personally wouldn't expect users to navigate the site this way, it's poor to not give the user the option to experience the site in this orientation on mobile.

- When clicked, a menu item hasn't been selected and the user decides to click on the page to collapse the dropdown menu, the heading dropdown menus within the boxing guide page maintain a lighter colour as if they're currently selected, despite that not being the case.

- On first load, the video background for index.html doesn't start. It does however play as intended on the second load onwards.

## Responsive Design Testing

### Hardware Used

The hardware used to test the responsive design of this project are as follows:

- Desktop/Laptop

  - Dell XPS 15

- Tablet

  - iPad

- Phone
  - iPhone 7
  - iPhone SE

### Software Used

The software used to text the responsive design of this project are as follows:

- Mozilla Firefox (Inc. Dev Tools)
- Google Chrome (Inc. Dev Tools)
- Microsoft Edge

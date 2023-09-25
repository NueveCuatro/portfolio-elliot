---
title: HCI - Lab1
publishDate: 2020-03-02 00:00:00
img: /assets/thumbnails/HCI-lab-1.png
img_alt: a personn scanning a document whith his phone
description: This is the blog entry for the lab 1 of HCI's course
tags:
  - HCI
  - Affordance
  - Dark Partern
---


### Affordances

#### Definition
Affordance is a concept in design and psychology that refers to the inherent usability or functionality of an object or environment, as perceived by a user. It describes the intuitive understanding a person has of how to interact with something based on its visual, tactile, or auditory cues. In essence, affordance is the property of an object or space that suggests its intended use or action.

#### Good Affordance: Elevator Buttons

<div style='text-align: center;'>
    <img src='/assets/images/HCI-lab-1/affordance2.jpg' alt="violation of gestalt's law of proximity" style='width: 50%;'>
</div>

**Explanation:**
Elevator buttons are an example of good affordance. They are typically designed with clear visual cues and feedback mechanisms. Each button is labeled with a number and is accompanied by a lit indicator to show whether it has been pressed or not. This design makes it easy for users to select their desired floor and see the status of their request.

**Suggested Improvement:**
While elevator buttons are generally good in terms of affordance, improvements can be made:

<u>Universal Design:</u> Ensure that elevator buttons are designed to be accessible to individuals with disabilities, including those who may have limited mobility or visual impairments. This may involve tactile indicators, audio feedback, and large, easy-to-press buttons.

<u>Sanitization:</u> Given concerns about hygiene, designers could explore touchless options, such as proximity sensors or smartphone apps for selecting floors, to minimize contact with buttons.

#### Bad Affordance: Public Restroom Faucets

<div style='text-align: center;'>
    <img src='/assets/images/HCI-lab-1/bad-affordance.png' alt="violation of gestalt's law of proximity" style='width: 50%;'>
</div>

**Explanation:**
In some public restrooms, the faucets have bad affordances. They often lack clear visual cues or markings to indicate how to activate them. Users may struggle to figure out whether they need to push, pull, twist, or wave their hands in front of the faucet to make it work, leading to confusion and frustration.

**Suggested Improvement:**
To improve this bad affordance, designers could consider:

<u>Clear Markings:</u> Add clear and simple instructions or symbols next to the faucet to indicate how it should be activated. For example, an icon showing a hand under the faucet to indicate that it's motion-activated.

<u>Consistency:</u> Make sure the activation method is consistent across all faucets in a facility. If motion sensors are used, ensure they are properly calibrated and responsive.

--- 

### Gestalt Law

#### Definition
Gestalt laws are principles of perceptual organization that help us understand how humans naturally group elements together to form meaningful patterns. When applied correctly, these principles can enhance user experiences.

#### Website Navigation - Proximity

<div style='text-align: center;'>
    <img src='/assets/images/HCI-lab-1/gestalt1.png' alt="violation of gestalt's law of proximity" style='width: 50%;'>
</div>

**Issue:**
On a news website, headlines and links to related articles are often placed too closely together. This violates the Gestalt principle of proximity, which states that objects that are close to each other are perceived as related. In this case, the close proximity of headlines and links can confuse users, making it unclear whether the links are part of the current article or related to other topics.

**Suggested Improvement:**
To correct this issue, the website could:

<u>Increase Spacing:</u> Add more space between the main article content and related links to visually separate them. This would make it clear that the links are not directly related to the current article.

<u>Visual Cues:</u> Use visual cues like borders, background colors, or icons to differentiate the related links from the main content. This helps users quickly identify which elements are related and which are not.

#### Mobile App Iconography - Similarity

<div style='text-align: center;'>
    <img src='/assets/images/HCI-lab-1/gestalt2.png' alt="violation of gestalt's law of similarity" style='width: 50%;'>
</div>

**Issue:**
In a mobile weather app, the icons for different weather conditions (e.g., sunny, rainy, cloudy) share similar shapes and colors. This violates the Gestalt principle of similarity, which states that similar elements are perceived as related. Users might have difficulty distinguishing between these icons, especially those with color vision deficiencies, leading to confusion about the current weather conditions.

**Suggested Improvement:**
To correct this issue, the app could:

<u>Distinct Icons:</u> Redesign the icons to have distinct shapes and colors for each weather condition. For instance, use a bright sun icon for sunny weather, a cloud with raindrops for rainy weather, and a partly cloudy icon for cloudy conditions. This ensures that users can easily differentiate between them.

<u>Accessibility Considerations:</u> Ensure that the color choices and icon designs are accessible to users with color vision deficiencies. Use high-contrast colors and consider using patterns or textures in addition to color to convey information.

---

### Dark pattern

#### Difficulty of Refusing Cookies on Websites

<div style='display: flex; justify-content: center;'>
    <img src='/assets/images/HCI-lab-1/cookie1.png' alt='cookie picture' style='width: 30%;'>
    <img src='/assets/images/HCI-lab-1/cookie2.png' alt='cookie picture' style='width: 30%; margin-left: 10px;'>
</div>

**Dark Design Pattern:**
Many websites employ dark patterns to make it challenging for users to refuse cookies or tracking. They often present cookie consent dialogs with a prominent "Accept" button and a less noticeable or unclear "Decline" or "Manage Preferences" option. This nudges users towards accepting cookies without fully understanding the implications.

**Redesign to Achieve the Opposite:**
To promote transparency and user empowerment in cookie consent dialogs, redesign them as follows:

<u>Clear Choices:</u> Clearly present users with distinct choices for managing cookies, such as "Accept All Cookies," "Accept Necessary Cookies Only," and "Customize Preferences." Use plain language to explain the purpose of each choice.

<u>No Pre-selection:</u> Do not pre-select any option, including the "Accept All Cookies" choice. Leave all options unselected by default, ensuring users actively make a choice.

<u>Educational Information:</u> Include a link to a clear and easily accessible privacy policy that explains the types of cookies used and their purposes. Provide users with the information they need to make an informed decision.

#### Pop-up Download Link on YouTube Videos

<div style='text-align:center;'>
    <img src='/assets/images/HCI-lab-1/youtube.png' alt='youtube dark pattern' style='width: 70%;'>
</div>

**Dark Design Pattern:**
On YouTube, a common dark pattern is the pop-up download link that appears when users attempt to skip an advertisement after a 5-second timer. This link can be misleading, as users expect to skip the ad but are instead prompted to download a potentially unwanted file.

**Redesign to Achieve the Opposite:**
To promote transparency and user empowerment in this scenario, redesign the interaction as follows:

<u>Clear and Predictable Behavior:</u> Ensure that clicking the "Skip Ad" button leads to the expected action of skipping the advertisement, without any pop-up download links. Keep the user's intent aligned with the outcome.

<u>Download Confirmation:</u> If there is a legitimate need to offer a download link, such as for an app or content related to the video, present it clearly and separately, not as a pop-up. Ask for explicit user consent before initiating any downloads.

<u>Educational Prompts:</u> Display brief educational prompts that inform users about how to avoid unwanted downloads and stay safe online. These prompts can encourage users to be cautious when encountering download links.
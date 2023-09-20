---
title: 'Creating My Blog with Astro: A Step-by-Step Guide'
publishDate: 2020-03-04 00:00:00
img: /assets/thumbnails/blog-creation.jpg
img_alt: no image yet
description: |
  This is the nice story of my portfolio's creation. 
tags:
  - astro
  - html - css
  - dns condfiguration
---

In the dynamic world of work and projects, I found myself in need of a dedicated space – a portfolio/blog – to not only showcase my accomplishments but also to rigorously document my journey. This digital diary, created using the Astro template, goes beyond a simple collection of posts; it serves as a means to document my work, obliging me to write a report each time I complete a project. This practice not only helps me keep a meticulous record of my achievements but also encourages self-reflection and personal growth.

Yet, my portfolio/blog offers more than just documentation. It acts as a bridge connecting me with anyone interested in my work. Serving as a hub, it provides a gateway for people to easily find my contact details, explore my resume, and learn more about me through my About Me page. It's a digital handshake, inviting collaboration and fostering connections.

Now, as we delve into this blog post, I'll guide you through the step-by-step process of how I brought this portfolio/blog to life, from setting it up to customizing it to perfectly suit my needs.

### Choosing the Right Template
One of the first decisions I had to make was choosing a suitable template for my blog. After some research, I settled on the Astro template due to its sleek and modern design. I was drawn to its simplicity and the potential for customization.

### Cloning the Project with `git`
Once I had chosen the Astro template, I needed to get the project files onto my local machine. I used Git to clone the template repository from GitHub. This allowed me to have a local copy of the template to work with.

```bash
$ git clone https://github.com/astro/blog-template.git
```

### Running It Locally with `npm`
To see how my blog looked and make changes, I needed to run it locally. I used npm (Node Package Manager) to set up the development environment and start a local server.


```bash
$ npm install
$ npm run dev
```

### Updating HTML and Information
The template came with default HTML and information that I needed to change to suit my portfolio/blog's needs. This included restructuring and modifying the HTML elements to create pages tailored to my content. I also updated my name, bio, and contact information to reflect my own details. I found these HTML files in the project and made the necessary updates.

### Updating Information
The template came with default information that I needed to change to reflect my own details. This included my name, bio, and contact information. I found these details in the project files and made the necessary updates.

### Adding Pictures
I personalized my blog by adding images to various sections. For example, I included a profile picture on the About Me page and added relevant images to my blog posts to make them visually engaging.

### Adding Clickable Icons
![clicable icons](/assets/images/blog-creation/clicable-icons.png)

To make it easy for readers to connect with me, I added clickable icons for my LinkedIn, GitHub, and email on the blog's header or footer. This way, visitors could easily find and reach out to me on these platforms.

### Styling and Theming
I wanted my blog to have a unique style, so I customized the colors, fonts, and overall styling of the pages. This involved modifying the CSS files in the project to match my personal aesthetic preferences.

<img src='/assets/images/blog-creation/download.png' alt='download picture of my site' style='width: 50%;'>

I wanted to provide visitors with easy access to my resume. I added a downloadable resume link on a dedicated page, allowing anyone interested to download my resume with a single click.

### Updating the About Page
I took the opportunity to update the content on the About Me page to provide a more detailed and personalized introduction to who I am and what my blog is all about.

### Deploying with Vercel
With my blog looking the way I wanted it to, it was time to deploy it to the web. I chose Vercel as my hosting platform due to its simplicity and integration with GitHub.

1. pushed my project to a GitHub repository.
2. connected my GitHub repository to Vercel.
3. configured the deployment settings, specifying the branch to deploy from.
4. Vercel automatically built and deployed my blog.
   
### Setting Up a Domain Name

<img src='/assets/images/blog-creation/dns.png' alt='download picture of my site' style='width: 50%;'>


To give my blog a professional touch, I purchased a domain name that reflected my blog's content. After obtaining the domain, I configured the DNS settings to point to my Vercel deployment, ensuring that my blog was accessible through the custom domain.

### Conclusion
Creating my blog using the Astro template was a rewarding experience. From choosing the template to customizing the design and deploying it to the web, every step allowed me to express my creativity and share my thoughts with the world. I hope this guide inspires you to start your own blogging journey!

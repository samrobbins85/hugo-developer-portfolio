+++
categories = ["web-dev"]
coders = []
date = 2020-06-19T23:00:00Z
description = "A portfolio website made with Hugo"
github = ["https://github.com/samrobbins85/hugo-developer-portfolio", "https://github.com/samrobbins85/portfolio-website"]
image = "https://res.cloudinary.com/samrobbins/image/upload/q_auto/v1591793276/logos/logos_hugo_h2xbne.svg"
title = "Hugo Portfolio Website"
type = "post"
[[tech]]
logo = "https://res.cloudinary.com/samrobbins/image/upload/v1591793276/logos/logos_hugo_h2xbne.svg"
name = "Hugo"
url = "https://gohugo.io/"
[[tech]]
logo = "https://res.cloudinary.com/samrobbins/image/upload/v1591793279/logos/logos_uikit_irc5gp.svg"
name = "UIkit"
url = "https://getuikit.com/"
[[tech]]
logo = "https://res.cloudinary.com/samrobbins/image/upload/q_auto/v1593603175/forestry-pos-full_lid6rs.svg"
name = "Forestry CMS"
url = "https://forestry.io/"

+++
I created my portfolio website using Hugo and UIKit, it serves as an online resume containing all my work.

This has been created as a theme so that others can use and adapt it.

## Sections

### Homepage

![Homepage Screenshot](https://res.cloudinary.com/samrobbins/image/upload/q_auto/v1591885280/screenshot_aexm2m.png "Homepage Screenshot")

The homepage provides the basic information about you, including links to social media, skills you have, things you've done and your education. This page makes good use of UIKit grid and cards for organising all the information and ensuring it is responsive to work on mobile devices. The hackathon section of this page uses code from [https://github.com/web-tiki/responsive-grid-of-hexagons](https://github.com/web-tiki/responsive-grid-of-hexagons "https://github.com/web-tiki/responsive-grid-of-hexagons") to ensure that the hexagons tile correctly.

### About

![About Screenshot](https://res.cloudinary.com/samrobbins/image/upload/q_auto/v1592844637/Screenshot_2020-06-22_Sam_Robbins_1_xop4uu.png "About Screenshot")

This is the page for a description about you, along with non-technical skills. This uses UIKit grid and cards in a very similar way to the homepage.

### Blog

![](https://res.cloudinary.com/samrobbins/image/upload/q_auto/v1593263737/Screenshot_2020-06-27_Sam_Robbins_koy2no.png)

If you want to have a blog, this page will serve that purpose. I may end up changing this to a column view rather than a column view in the future, but for the present I think it looks fine.

### Portfolio

![](https://res.cloudinary.com/samrobbins/image/upload/q_auto/v1593263791/Screenshot_2020-06-27_Sam_Robbins_1_xa3yvj.png)

This allows you to describe the projects you have created in order to showcase them to people looking at your site.

### Contact

![](https://res.cloudinary.com/samrobbins/image/upload/q_auto/v1593263826/Screenshot_2020-06-27_Sam_Robbins_ce7qsx.png)

This provides a simple contact form which allows users of the site to send you a message. I implemented this using [https://formspree.io/](https://formspree.io/ "https://formspree.io/") as it has a generous free plan and is very simple to integrate.

## Installation

### Integrating into your site

To install this theme, first create a themes folder in your site with

```bash
mkdir themes
```

Then move into this directory with

```bash
cd themes
```

The repository can then be added either by cloning or adding as a submodule

```bash
# Cloning
git clone https://github.com/samrobbins85/hugo-developer-portfolio hugo-developer-portfolio
# Submodule
git submodule add https://github.com/samrobbins85/hugo-developer-portfolio hugo-developer-portfolio
```

In the `config.toml` file in your site directory add

```toml
theme="hugo-developer-portfolio"
```

### Creating a new site

If you just want to get set up with a new site, you can start from the Example Site I have provided. To do this:

1. Cut the `exampleSite` folder out of the theme and paste it wherever you want
2. Create a `theme` directory within the `exampleSite folder`
3. Paste the theme into this directory, ensuring is has the name `hugo-developer-portfolio`

## CMS

For the content management system I have used Forestry CMS. This provides great flexibility for adding and editing content and integrates great with Hugo as it commits markdown files directly to GitHub.

## Configuration

This is a highly configurable site, and as such, it will be unlikely that it will work with your existing site.

### Config.toml

`Config.toml` provides the basic structure of the site, it contains a range of sections

#### Base information

In the example site, the base information looks as follows

```toml
baseURL = "http://example.com" # The URL of your site
languageCode = "en-gb" # The language you want to display the site in
title = "Sam Robbins" # The title you want to appear in the address bar
theme = "hugo-developer-portfolio" # The theme, don't change this
```

#### Plugins

These are the essential plugins required to run the site, but you can add more if you need

```toml
[params.plugins]
  # CSS Plugins
  [[params.plugins.css]]
  URL = "https://cdn.jsdelivr.net/npm/uikit@3.2.6/dist/css/uikit.min.css"
  # JS Plugins
  [[params.plugins.js]]
  URL = "https://cdn.jsdelivr.net/npm/uikit@3.2.6/dist/js/uikit.min.js"
  [[params.plugins.js]]
  URL = "https://cdn.jsdelivr.net/npm/uikit@3.2.6/dist/js/uikit-icons.min.js"
```

#### Navigation

This specifies the titles for the entries in the taskbar. `name` can be changed to show a different name. `URL` should not be changed in most situations as the pages will exist at the old URLs rather than the new ones, so this will result in dead links.

```toml
# navigation
[menu]
  [[menu.main]]
  name = "About"
  URL = "about"
  [[menu.main]]
  name = "Blog"
  URL = "blog"
  [[menu.main]]
  name = "Portfolio"
  URL = "portfolio"
  [[menu.main]]
  name = "Contact"
  URL = "contact"
```

#### Params

This contains the other configuration information

```toml
[params]
home = "Home" # What you want the homepage to show up as in the menu bar
# Meta data
description = "The website of Sam Robbins, 2nd Year Computer Science Student at Durham University"
author = "Sam Robbins"


  [params.contact]
  formAction = "https://formspree.io/<Insert code>" # Add your formspree URL here to get emails

  # This contains the contact information for the footer
  [params.footer]
  email = "samrobbinsgb@gmail.com"
  address = "Durham, UK"
  googlemaps = "https://www.google.com/maps/embed/v1/place?q=place_id:ChIJwbHYJaUqfEgRK0Ui9dVGimc&key=AIzaSyAE_4rVAKux_DSPcb_OdSRDaovtPOSk_3U"
```

### homepage.yml

This file is stored in `data/homepage.yml`. It determines the content of the homepage and contains many sections

#### banner

This is the text in the hero section, change it to whatever you want

```yml
banner:
  title: Hi! I’m Sam
```

#### social

Put all of your social links here and they will appear in the social section

```yml
social:
  twitter: ""
  linkedin: sam-robbins-gb
  github: samrobbins85
  gitlab: ""
  facebook: ""
  instagram: ""
  gmail: samrobbinsgb
```

#### about

* `enable` can be used to hide this section
* `content` determines what text is shown here
* `btnText` changes the text on the button
* `URL` changes the URL the button directs to

```yml
about:
  enable: true
  content: 2nd Year Durham Computer Science Student
  button:
    btnText: Find out more
    URL: "/about"
```

#### skill

* `enable` can be used to hide this section
* `title` determines the text both under the image and in the modal
* `logo` determines the image that shows up
* `description` is the text that appears inside the modal

```yml
skill:
  enable: true
  item:
    - title: JavaScript
      logo: https://res.cloudinary.com/samrobbins/image/upload/v1591793272/logos/logos_javascript_adj1dx.svg
      description: Details coming soon, contact me if you want to know more
```

#### experience

* `enable` can be used to hide this section
* `logo` determines the image that shows up
* `title` is the main text that appears in the card
* `company` is the secondary text in the card
* `duration` is the tertiary text in the card

```yml
experience:
  enable: true
  item:
    - logo: https://res.cloudinary.com/samrobbins/image/upload/f_auto,q_auto/v1591793271/logos/logos_google_id6v9a.svg
      title: init.g
      company: Google
      duration: November 2019
```

#### hackathons

```yml
hackathons:
  enable: true
  item:
    - title: Hack Cambridge 2019
      description: Climate change simulator
      image: https://res.cloudinary.com/samrobbins/image/upload/f_auto,q_auto/v1591793405/stickers/Hack_Cambridge_101_ozoq5d.png
      url: javascript:void(0)
```
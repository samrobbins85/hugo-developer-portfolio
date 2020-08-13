![GitHub](https://img.shields.io/github/license/samrobbins85/hugo-developer-portfolio?style=for-the-badge)

# Developer Portfolio

![Website Image](https://res.cloudinary.com/samrobbins/image/upload/v1591885280/screenshot_aexm2m.png)

## Features

- Responsive Design
- Blog Section
- Portfolio Section
- Homepage to show off skills

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

The exampleSite folder is all set up to work as a site, just copy it out of the Git repo and it will work. You need to have golang installed as it uses [hugo modules](https://gohugo.io/hugo-modules/use-modules/).

## Configuration

This is a highly configurable site, and as such, it will be unlikely that it will work with your existing site.

### `Config.toml`

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

### `homepage.yml`

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

- `enable` can be used to hide this section
- `content` determines what text is shown here
- `btnText` changes the text on the button
- `URL` changes the URL the button directs to

```yml
about:
  enable: true
  content: 2nd Year Durham Computer Science Student
  button:
    btnText: Find out more
    URL: "/about"
```

#### skill

- `enable` can be used to hide this section
- `title` determines the text both under the image and in the modal
- `logo` determines the image that shows up
- `description` is the text that appears inside the modal

```yml
skill:
  enable: true
  item:
    - title: JavaScript
      logo: https://res.cloudinary.com/samrobbins/image/upload/v1591793272/logos/logos_javascript_adj1dx.svg
      description: Details coming soon, contact me if you want to know more
```

#### portfolio

This is used to highlight specific portfolio projects you want to show

- `enable` can be used to hide this section
- `title` is the text at the top each item
- `image` is the image for each item
- `description` goes underneath the image for each item
- `link` directs to the main portfolio page
- `tools` indicates what technologies you used, it uses the icons from https://simpleicons.org/

```yml
portfolio:
  enable: true
  item:
    - title: Easy DMARC
      image: https://res.cloudinary.com/samrobbins/image/upload/v1597159067/Easy_DMARC_hkcgif.webp
      description: A website to make it easy to add DMARC to a Vercel website
      link: "/portfolio/easy-dmarc"
      tools:
        - next-dot-js
        - tailwindcss
        - vercel
        - react
```

#### experience

- `enable` can be used to hide this section
- `logo` determines the image that shows up
- `title` is the main text that appears in the card
- `company` is the secondary text in the card
- `duration` is the tertiary text in the card

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

By placing none in the URL field, the image will be rendered without any links

```yml
hackathons:
  enable: true
  item:
    - title: Hack Cambridge 2019
      description: Climate change simulator
      image: https://res.cloudinary.com/samrobbins/image/upload/f_auto,q_auto/v1591793405/stickers/Hack_Cambridge_101_ozoq5d.png
      url: none
```

#### certifications

This allows you to list your certifications in the following format

```yml
certifications:
  enable: true
  item:
    - title: Microsoft Azure Fundamentals
      image: https://res.cloudinary.com/samrobbins/image/upload/v1592501459/microsoft-certified-fundamentals-badge_cpcgyn.svg
      url: https://www.youracclaim.com/badges/b4cf7a86-eb83-478e-bfd0-9f427c3474a0/public_url
```

#### Awards and Achievements

This allows you to list your awards and achievements in the following format

```yml
awards:
  enable: true
  item:
    - title: Phase 1 Winner
      event: GNOME Community Engagement Challenge
      image: https://res.cloudinary.com/samrobbins/image/upload/v1595701167/CEChallenge-P1Winner2_iyjvyu.png
```

#### education

This section allows you to showcase your education history, the fields are self explanatory.

```yml
education:
  enable: true
  item:
    - title: BSc Computer Science
      year: 2018 - Present
      academy: Durham University
      image: https://res.cloudinary.com/samrobbins/image/upload/f_auto,q_auto/v1591793268/logos/logos_Durham_fc2sae.svg
```

### `about.yml`

This file configures the about page, and follows the format below:

```yml
leadership:
  enable: true
  item:
    - logo: https://res.cloudinary.com/samrobbins/image/upload/f_auto,q_auto/v1591793280/logos/logos_yl_qozav6.webp
      title: Young Leader
      company: The Scout Association
      duration: September 2014 - July 2018
```

### `porfolio.yml`

This file configures the portfolio page, allowing you to specify the filters you want to use.

```yml
filter:
  - label: Web Dev
    value: web-dev
```

### Blogs

When submitting a blog, you can supply the following fields in the front matter

```yml
title: "Making a new Website"
date: 2019-12-31T12:14:34+06:00
image: "https://d33wubrfki0l68.cloudfront.net/c38c7334cc3f23585738e40334284fddcaf03d5e/2e17c/images/hugo-logo-wide.svg"
description: "My first blog, introducing my new website"
author: "Sam Robbins"
```

### Portfolio pages

The portfolio page and blog page use the same configuration, so you can use these new fields if you want, but they are more suited to portfolio pages

```toml
categories = ["hackathon", "web-dev"]
coders = ["samrobbins85", "karina-talibzhanova"]
date = 2020-05-30T23:00:00Z
description = "A Firefox Browser Extension"
github = ["https://github.com/karina-talibzhanova/oxfordhack2020"]
image = "https://res.cloudinary.com/samrobbins/image/upload/q_auto/v1593352345/twoo-home_k7molq.png"
title = "Oxford Digithon"
[[tech]]
logo = "https://res.cloudinary.com/samrobbins/image/upload/q_auto/v1591793272/logos/logos_javascript_adj1dx.svg"
name = "JavaScript"
url = "https://www.ecma-international.org/memento/tc39.htm"
[[tech]]
logo = "https://res.cloudinary.com/samrobbins/image/upload/q_auto/v1593368547/firefox-ar21_cps6me.svg"
name = "Firefox WebExtensions"
url = "https://www.mozilla.org/en-GB/firefox/"
```

The [[tech]] item can be repeated as many times as you desire.

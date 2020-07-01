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

If you just want to get set up with a new site, you can start from the Example Site I have provided. To do this:

1. Cut the `exampleSite` folder out of the theme and paste it wherever you want
2. Create a `theme` directory within the `exampleSite folder`
3. Paste the theme into this directory, ensuring is has the name `hugo-developer-portfolio`

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

#### leadership

This configures the cards you can see on the "About me page"

```yml
leadership:
  enable: true
  item:
    - logo: https://res.cloudinary.com/samrobbins/image/upload/f_auto,q_auto/v1591793280/logos/logos_yl_qozav6.webp
      title: Young Leader
      company: The Scout Association
      duration: September 2014 - July 2018
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

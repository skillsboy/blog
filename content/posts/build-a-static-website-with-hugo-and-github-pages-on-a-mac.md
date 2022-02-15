---
title: "Build a Static Website With Hugo and Github Pages (Mac)"
date: 2021-12-04T12:00:00Z
draft: true
cover:
  image: "images/cover/hugo+GitHubPages.png" # image path/url
  alt: "Hugo + GitHub Pages" # alt text
  #caption: "<text>" # display caption under cover
---

## Intro

This tutorial will show you how to create a Static Website with Hugo and then deploy It on GitHub Pages for free.

Great for a Personal Portfolio or Blog.

## What is...

> <a href="https://gohugo.io/" target="_blank">Hugo</a>
>
> Fast and modern static site generator written in Go.

> <a href="https://pages.github.com/" target="_blank">GitHub Pages</a>
> 
> Static site hosting service, for free!

## Tutorial

### 1. Requirements

<div style="margin-left: 20px">

  Open your terminal and copy the following commands.

  > Homebrew
  >
  > ```
  > /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
  > ```

  > Git
  >
  > ```bash
  > brew install git
  > ```

  > Hugo
  >
  > ```bash
  > brew install hugo
  > ```

</div>

---

### 2. Create Hugo Site

#### 2.1. Set up a site:

<div style="margin-left: 20px">

  > First go to the directory where you want to save your hugo site (E.g., ```dev``` folder).
  >
  > ```bash
  > cd ~/dev/
  > ```

  > Create a new hugo site (E.g., ```blog```).
  >
  > This will create a directory called ```blog``` with a pre-made folder structure.
  >
  > -f flag is so instead of toml we use yaml for our config and for the markdown front matter.
  >
  > <span style="font-size: 12px">~/dev/ %</span>
  > ```bash
  > hugo new site blog -f "yaml"
  > ```
  >
  > <p align="center">
  >   <img width="200" src="/images/build-a-static-website-with-hugo-and-github-pages-1.png">
  > </p>

</div>

#### 2.2. Add a theme

<div style="margin-left: 20px">

  Now that the site is created, the next step is to add a theme to the ```themes``` directory.  
  Themes can be found in <a href="https://themes.gohugo.io/" target="_blank">Hugo Themes</a>.

  > First enter the projects root.
  >
  > <span style="font-size: 12px">~/dev/ %</span>
  > ```
  > cd blog
  > ```

  > Clone the chosen theme (E.g., ```hugo-PaperMod```) into the themes folder.
  >
  > <span style="font-size: 12px">~/dev/blog/ %</span>
  > ```bash
  > git clone https://github.com/adityatelange/hugo-PaperMod.git themes/
  > ```
  >
  > <p align="center">
  >   <img width="200" src="/images/build-a-static-website-with-hugo-and-github-pages-2.png">
  > </p>

  > Open the config file and add to the end of the file a property called ```theme``` with the directory name of the chosen theme  (E.g., theme: ```hugo-PaperMod```).
  >
  > <p align="center">
  >   <img width="200" src="/images/build-a-static-website-with-hugo-and-github-pages-3.png">
  >   <img width="300" src="/images/build-a-static-website-with-hugo-and-github-pages-4.png">
  > </p>

</div>

---

### 3. Test the local site

> This will provide us a local webserver, where we can see live changes.
>
> <span style="font-size: 12px">~/dev/blog/ %</span>
> ```bash
> hugo server
> ```
>
> <p align="center">
> 	<img src="/images/build-a-static-website-with-hugo-and-github-pages-5.png">
> 	<img src="/images/build-a-static-website-with-hugo-and-github-pages-6.png">
> </p>

---

### 4. Deploy on GitHub Pages

#### 4.1. Create a new git repository

<div style="margin-left: 20px">

  > In your github create a new repository (E.g., ```blog```) and make sure it is set as ```Public```.

</div>

#### 4.2. Link Hugo site to the new git repository

<div style="margin-left: 20px">

  > Don't forget to change to your github username.
  >
  > <span style="font-size: 12px">~/dev/blog/ %</span>
  > ```bash
  > git init &&
  > git branch -M main &&
  > git remote add origin https://github.com/skillsboy/blog.git
  > ```

</div>

#### 4.3. Prepare files

<div style="margin-left: 20px">

  > There is a ```.git``` file inside the chosen theme directory, this file has to be removed because when we try to push the Hugo project to github It may not work.
  >
  > <span style="font-size: 12px">~/dev/blog/ %</span>
  > ```bash
  > rm -rf themes/hugo-PaperMod/.git
  > ```

  > Change the baseURL of the Hugo site, this is done inside the config file.
  >
  > Don't forget to change to your github username.
  > <p align="center">
  >	<img width="200" src="/images/build-a-static-website-with-hugo-and-github-pages-3.png">
  >	<img width="300" src="/images/build-a-static-website-with-hugo-and-github-pages-7.png">
  > </p>

  > Build the static files.
  >
  > This will create a ```public``` folder where Hugo will generate all the static files.
  >
  > <span style="font-size: 12px">~/dev/blog/ %</span>
  > ```bash
  > hugo
  > ```
  >
  > <p align="center">
  >   <img width="150" src="/images/build-a-static-website-with-hugo-and-github-pages-9.png">
  > </p>

</div>

#### 4.4. Deploy

<div style="margin-left: 20px">

  >  First Push Hugo files to the main branch repository.
  >
  > <span style="font-size: 12px">~/dev/blog/ %</span>
  >```bash
  > git add . &&
  > git commit -m "first deploy" &&
  > git push -u origin main 
  >```

  > Then push the static files from inside the public folder to the root of another branch called ```gh-pages```.
  >
  > <span style="font-size: 12px">~/dev/blog/ %</span>
  >```bash
  > git subtree push --prefix public origin gh-pages
  >```

  After a few seconds the site will be online, at ```https://skillsboy.github.io/blog/```.  
  (Don't forget to change to your github username)

</div>

<br><p align="center" style="font-size: 30px;">Have fun 😄</p>
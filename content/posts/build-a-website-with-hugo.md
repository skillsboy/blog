---
title: "Build a Website With Hugo"
date: 2022-02-16T15:40:15Z
draft: false
---

This tutorial is going to show you how to build a Website with Hugo.  
Great for a Personal Portfolio or a Blog.

![Hugo website final result](/images/build-a-website-with-hugo-final-result.png#center)

### Requirements

* <a href="https://gohugo.io/getting-started/installing/" target="_blank">Hugo</a>

### Create a new hugo site

**1. New site**

```bash
hugo new site websiteName -f "yaml"
```
* ``websiteName`` is the name of the site that is going to be created.
* ``-f`` flag is so instead of the default toml we use yaml for our config and for the markdown front matter.

This will create a folder called ``websiteName`` with the following structure.

> ├── archetypes  
> ├── config.yaml  
> ├── content  
> ├── data  
> ├── layouts  
> ├── static  
> └── themes

### Add a theme

**1. Change directory**

```bash
cd websiteName
cd themes
```

**2. Download theme**

{{<pwd>}}~websiteName/themes/ %{{</pwd>}}

```bash
git clone https://github.com/adityatelange/hugo-PaperMod.git
```

A ``hugo-PaperMod`` folder will be created inside the themes, themes can be found <a href="https://themes.gohugo.io/" rel="noreferrer" target="_blank">here</a>.

**3. Now we have to activate it. To do that go back to the projects root.**

{{<pwd>}}~websiteName/themes/ %{{</pwd>}}

```bash
cd ..
```

**4. Activate**

Open ``config.yaml``.  
Add:

```bash
theme: hugo-PaperMod
```

![Hugo add theme](/images/build-a-website-with-hugo-add-theme.png#center)

### Test local site

**1. Test**

{{<pwd>}}~websiteName/ %{{</pwd>}}

```bash
hugo server -D
```

* ``-D`` flag will include all posts marked as ``draft: true`` in there front matter.

This will create a live server.

![Hugo test site](/images/build-a-website-with-hugo-test-site.png#center)

**2. Navigate with your browser to the given url.**

![Hugo website final result](/images/build-a-website-with-hugo-final-result.png#center)

### Build static files for production

**1. Add baseURL**

Open ``config.yaml``.  
Change:

```bash
baseURL: https://yourDomain.com
```

Add your domain, this has to be done because when hugo generates the static files it may use absolute paths.

**2. Build static files**

{{<pwd>}}~websiteName/ %{{</pwd>}}

```bash
hugo
```

This will create a folder called ``public`` in the projects root, where all the static files will be generated. 

**3. Copy /public/***

Now just copy those files, from inside the public folder, to your webserver and you will be able to see the default page from the chosen theme.  

<br>

{{<endMessage>}}Have fun 😄{{</endMessage>}}
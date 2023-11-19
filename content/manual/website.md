---
title: Creating the website
summary: Some details about this website, how it was created, where it lives, etc, and how to make minor updates.
date: 2023-01-06

reading_time: false  # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?
view: compact
lastmod: 2023-01-22
#authors: ["FrajkaWilliams-Eleanor"]
tags: []
private: true

weight: 1000

# Optional header image (relative to `assets/media/` folder).
header:
  caption: ""
  image: ""
---

This website uses a Hugo site with the Wowchemy template 'Research Group'.  It is hosted on Github, served by Netlify and has a custom domain from Google domains.

{{< toc >}}




## Getting started

Previously, I'd used a 'Feeling Responsive' theme for Jekyll on Github, but this became cumbersome to keep up-to-date (too complicated).

After googling for 'research group website', I found one I liked and followed their instructions:
[How to Build Academic Website for Research Group in 2021](https://jedyang.com/post/how-to-build-academic-research-group-website-in-2021/)

I didn't follow *all* the instructions, but stuck to:
1. [Hugo](https://gohugo.io/) static web generator
2. [Wowchemy](https://wowchemy.com/) research group template
3. [Github](https://github.com/)
4. [Netlify](https://www.netlify.com/)
5. [Google domain](https://domains.google.com) - mostly because this is where I'd previously purchased a domain name.

Some other examples for how-to are by [Ashis Saha](https://alorchhota.github.io/post/2021-01-26_personal_website/).

## Implementation

### Hugo, Wowchemy + Github

I followed the [Hugo installation guide](https://gohugo.io/getting-started/installing/) which required installing [Homebrew](https://brew.sh/) on my Mac and then

```
brew install hugo
```

I also needed [Go](https://go.dev/doc/install).

I then cloned the Wowchemy `Research group' theme onto my computer.  In that directory, I can run

```
hugo server
```

and my site shows up locally at ```localhost:1313``` (entered into the location bar of a browser window).  After making necessary changes, I use the Github desktop app to commit the changes, and then push to origin.  At this point, they become visible on the Netlify version of the website.

### Basic updates

All the basic customisation is given in [Hugo Site Customization](https://wowchemy.com/docs/getting-started/customization/) including:
- Personalising the domain name: [Get Your Own Domain Name](https://wowchemy.com/docs/hugo-tutorials/domain/).  I had a google domain so I followed the instruction to link them on Netlify.
- Adding a website icon.  I had a previou *favicon* so I followed the instructions for this.
- Change the font to 'medium' from the default 'large'.  (The publications information became too hard to read otherwise.)
- Shortening the website name in *config/_default/params.yaml* since it was too long for a mobile rendering of the website (website name was overlying the menu).
- Left default colors *minimal* and fonts *native*
- Updated the menu choices to my preferred option: "Research", "Teaching", "Publications", "Group" - but with the url pointing to the UHH website, "Manual" - where there is a new starter guide that I patterned after [E Wallace](https://ewallace.github.io/manual/newstart), and "News".  I'm still debating/figuring out how to add a "Data" menu patterned after "Publication" and possibly an "Events" menu which is forward-looking for upcoming events/talks (rather than "News" which is backwards).

### Creating the publications list

I started by using the command-line tool ([instruction here](https://wowchemy.com/docs/content/publications/))to create the publications directories from a "*.bib" file.  This required

```
pip3 install -U academic
```
Then importing my publications from the website main directory (GitHub/ifmeo) using
```
academic import --bibtex data/publications.bib
```
This is easiest if the *publications.bib* file already has the paper abstracts in it, as well as the doi number.  Otherwise, these can be added later but re-running this may overwrite the directories and you'll have to do all the manual edits again.

This creates a subdirectory for each bibtex entry, where the naming convention is based on the citekeys.  Within each directory is an *index.md* file and a *cite.bib* file, where the citation can be downloaded, and the *index.md* contains a bunch of information about the publication.

Manual edits to the *index.md* file that I found necessary were:
- Change my author name to match the folder/username specified in the content/authors/ directories
- Add tags, where various tags I found relevant for my work were "AMOC", "gliders", "Southern Ocean", "mesoscale", "submesoscale", "bottom pressure", "methods", "mixing", "Labrador Sea".  I'm not quite sure whether the names are case sensitive or not, but I needed to create the directory *content/tags/* with a subdirectory for each tag, like *content/tags/gliders* which contains an *_index.md* file where the title is changed to "Gliders".  This is the name that will appear in the Tag at the bottom of each publication, and it is case-sensitive/space-sensitive, etc.
- In a few cases, I've added a featured.jpg to the directory for a publication
- In some cases, adding the project name to the *projects: [projectname]* list if I had created a *content/project/projectname/* entry.
- In some cases (*need to update all*) I've added the `url_pdf: ` to the header as well, for the URL where the publication is contained in an institutional archive (in case the reader doesn't have a subscription to the journal in question).

#### More complex changes:

I'd like to change the *publications_type* that is refereneced by each *content/publication/frajkawilliams-etal-2011* to also include a type for "Dataset" and "Grey literature".  At the moment, the list is
```
0 = Uncategorized
1 = Conference paper
2 = Journal article
3 = Preprint / Working Paper
4 = Report
5 = Book 
6 = Book section
7 = Thesis
8 = Patent
```
but I don't need the `Patent` item, and possibly not the `Uncategorized` option.  This appears editable in

> **Modifying Publication Types**
>
> To rename publication types, edit the associated pub_* values in your language pack. If your language pack hasn’t been updated recently, you can copy the latest options from the English language pack.

To do this, I followed the instructions [here]() to download the English language pack into a new folder ```ifmeo/i18n/``` as ```ifmeo/content/en.yaml```.  Within this, I scrolled down to ```id: pub_patent``` and changed the translation to ```Dataset```.

So my list is now
```
0 = Uncategorized
1 = Conference paper
2 = Journal article
3 = Preprint / Working Paper
4 = Report
5 = Grey literature 
6 = Book section
7 = Thesis
8 = Dataset
```

### Updating the website

Updating the website can be done in the Github repository, in which case new changes need to be *fetched* and *pulled* to update the repository on my computer.  I don't use the more robust option specified by [Jed Yang's instructions](https://jedyang.com/post/how-to-build-academic-research-group-website-in-2021/).

#### Adding a new publication

I do this from the command line as ([instruction here](https://wowchemy.com/docs/content/publications/))
```
hugo new content/publication/<my-publication>
```
Then edit the contents of the *index.md* file.

#### Adding a new dataset

Again, as for publications, I do this from the command line as ([instruction here](https://wowchemy.com/docs/content/publications/))
```
hugo new content/publication/data-YYYY-ID
```
where all datasets start with ```data``` then the year the data end (for moorings from 2017-2018, use 2018) is the ```YYYY``` and the ID is some other identifying information: either the cruise information, like MSM21 for a Merian cruise 21, or project ```rapid``` or mooring name like ```DS2```.


Then edit the contents of the *index.md* file.  Here, the publication type is 8 or ["8"], the category is ["data"] and if applicable, the project is ["dsow"] or ["rapid"] or ["terific"].  
- Within the ```index.md``` file, the ```date: YYYY-MM-DDTHH:MM:SS``` must be entered in this format.  If only the year is known, then enter the year followed by ```2018-01-01T12:00:00```.  (The date can be adjusted to order datasets sequentially.)
- The publication is the data centre holding the data, e.g. "British Oceanographic Data Centre" with ```publication_short: "BODC"``` or ```publication: PANGAEA``` or ```publication: SEANOE```.
- The shortened abstract (```summary:```) should include the data type (e.g., moored CTD, hydrographic CTD) and date range of the data to nearest month and year.
- Enter the ```url_dataset:``` if known.

For datasets downloaded from PANGAEA, the bibtex citation information can also be downloaded to the publication folder, and then renamed to ```cite.bib```.

*Later updates:* Add a map with the data location.  This can be a static map, screenshot from PANGAEA or similar.


#### Adding a new person

This is explained in the [Hugo steps to customise a theme](https://wowchemy.com/docs/content/authors/) but I've modified it somewhat (not sure whether things will break later) to use lastname-firstname.

```
hugo new content/authors/Lastname-Firstname
```

Then, within the new folder, edit ```_index.md``` fixing the order of the name in title, adding  the role (e.g. PhD student, Technician, Research Scientist) and update the user_groups to 'Group'.



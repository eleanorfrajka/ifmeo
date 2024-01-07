---
# Leave the homepage title empty to use the site title
title: 'TERIFIC project (2018-2025)'
subtitle: An ERC starting grant fellowship with gliders and drifters in the Labrador Sea.
summary: "Targeted Experiment to Reconcile Increased Freshwater with Increased Convection. ERC fellowship with gliders and drifters in the Labrador Sea."
date: 2022-10-24
type: landing

# Show the page's date?
show_date: false
# Show estimated reading time?
reading_time: false
# Show social sharing links?
share: false
# Show author profile (photo and bio) under the content?
# Edit your author profiles in the `content/authors/` folder
# Then reference their folder names with the `authors` front matter option above
profile: false
# Allow users to comment on the page?
# Requires commenting to be configured in `params.yaml`
commentable: false
# Allow visitors to make improvements to the page?
# Requires a repository to be configured in `params.yaml`
editable: false
# Show a link to the next article in the series?
pager: false
# Show breadcrumb navigation?
show_breadcrumb: true

# Hide the navigation bar?
# Often used together with `show_breadcrumb`
header:
  navbar:
    enable: true

authors: 
- Eleanor Frajka-Williams
- Louis Clement
- Elodie Duyck
- Emelie Breunig
- Boris Shapkin
- Katja Schultz
- Yves Sorge
tags: [AMOC]
doi: 10.3030/803140
categories: [project]

# Cover image
# To use, place an image named `featured.jpg/png` in your page's folder.
# Otherwise, specify the `filename` option to load an image from your `assets/media/` folder.
# Placement options: 1 = Full column width, 2 = Out-set, 3 = Screen-width
# Focal point options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
# Set `preview_only` to `true` to just use the image for thumbnails.
sections:
  - block: markdown
    id: section-1
    content:
      title: TERIFIC project (2018 - 2025)
      subtitle:
    design:
      spacing:
        padding: ['20px','0','20px','0']
  - block: markdown
    id: funding
    content:
      title: 
      text: 'The ocean Meridional Overturning Circulation (MOC) is responsible for poleward heat transport, and deep storage of heat and carbon. Climate models generally predict that a slowdown of the MOC will occur this century, with dramatic regional and global climate changes, but how the slowdown will occur is subject to debate. It is widely recognised that convection – the downward limb of the MOC – is sensitive to freshwater fluxes, and recent investigations have suggested that the increased melt from the Greenland Ice Sheet has already reduced convection. Yet in 2015, convection returned, and was anomalously strong. Despite the expectation that the MOC is sensitive to freshwater forcing, we do not understand the processes by which freshwater inputs influence the MOC.
      <br><br>
      The two key gaps in our understanding are: how freshwater reaches the regions of deep convection, and the relative importance of freshwater to convection and restratification. Numerical simulations give conflicting results on freshwater pathways, and convective parameterisations neglect small-scale restratifying processes. Traditional observational approaches cannot capture the spatial and temporal variability of these processes without inordinate cost.
      <br><br>
      TERIFIC (2018-2023 + 2) addresses these gaps in understanding through new observations, leveraging recent advances in small-scale electronics to deploy large numbers of mini-drifters on the shelves of Greenland, and employing subsurface and surface autonomous platforms to characterise the balance of processes controlling convection and restratification. The analysis of these observations will answer fundamental questions about how freshwater reaches and affects the regions of deep convection, and enable a critical ground truth of numerical simulations of these processes for climate models.'
    design:
      columns: '1'
      spacing:
        padding: ['20px','0','20px','0']
  - block: hero
    content: 
      title: ''
      image:
        filename: featured_terific.png
      text: "A schematic of the meridional overturning circulation where red lines show the northward flowing warm waters, and the blue lines, the deep water formed through open ocean convection."
  - block: markdown
    id: funding
    content:
      title: Funding
      text: 'TERIFIC (Targeted Experiment to Reconcile Increased Freshwater with Increased Convection) is a 5-year ERC Starting Grant fellowship (Nov 2018 - Oct 2023 + 2 years) under the Horizon 2020 research and innovation programme, led by Eleanor Frajka-Williams (NOC).  It has two major fieldwork components: using drifters around the shelves of Greenland and autonomous surface and underwater vehicles in the Labrador Sea.  

      - EU grant number [803140](https://cordis.europa.eu/project/id/803140) with doi [10.3030/803140](http://dx.doi.org/10.3030/803140).'
    design:
      columns: 2
      spacing:
        padding: ['20px','0','20px','0']
  - block: collection
    id: posts
    content:
      title: Recent Posts
      subtitle: ''
      text: ''
      # Choose how many pages you would like to display (0 = all pages)
      count: 3
      # Filter on criteria
      filters:
        folders:
          - post
        author: ""
        category: ""
        tag: "terific"
        project: "terific"
        exclude_featured: false
        exclude_future: false
        exclude_past: false
        publication_type: ""
      # Choose how many pages you would like to offset by
      offset: 0
      # Page order: descending (desc) or ascending (asc) date.
      order: desc
    design:
      # Choose a layout view
      view: showcase
      columns: '2'
  - block: collection
    content:
      title: Related Publications
      text: 
      filters:
        folders:
          - publication
        exclude_featured: false
        tag: ""
        category: "terific"
        author: ""
        publication_type: ""
    design:
      columns: '2'
      view: citation
      
  - block: markdown
    content:
      title: TERIFIC1 in December 2019
      subtitle: ''
      text: |-
        {{< gallery album="terific1" >}}
    design:
      columns: '1'
  - block: markdown
    content:
      title: TERIFIC3 in December 2021
      subtitle: ''
      text: |-
        {{< gallery album="terific3" >}}
    design:
      columns: '1'
---

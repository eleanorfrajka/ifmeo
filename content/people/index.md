---
title: Group
date: 2024-09-02

reading_time: false  # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?

# Optional header image (relative to `assets/media/` folder).
header:
  caption: ""
  image: ""

type: landing

sections:
  - block: people
    id: people
    content:
      title: 
      # Choose which groups/teams of users to display.
      #   Edit `user_groups` in each user's profile to add them to one or more of these groups.
      user_groups:
          - Principal Investigator
          - Group
#          - Researchers
#          - Grad Students
#          - Administration
#          - Visitors
          - Alumni (Hamburg)
      sort_by: Params.last_name
      sort_ascending: true
    design:
      show_interests: false # show interests?
      show_role: true
      show_social: true  # show user's social networking links?
      show_organizations: false
  - block: markdown
    id: section-1
    content:
      title: Join the group
      subtitle: 
      text: 'If you are interested in joining the EO group, please contact us.  

        - For students (MSc and BSc), priority is given to UHH students planning dissertations in the [Oceanography/Geophysics](https://www.ifm.uni-hamburg.de/education/bachelor.html) (BSc) or [Ocean and Climate Physics](https://www.ifm.uni-hamburg.de/en/education/master.html) (MSc) programs.  

        - PhD students are usually hired through the [IMPRS graduate school](https://mpimet.mpg.de/en/career/imprs-esm) with a deadline by the middle of September each year. 

        - We anticipate hiring postdocs on the [PycnMIX project](../project/pycnmix) in the next year, and through the [CLICCS2 Cluster of Excellence: Ocean Circulation project](../project/cliccs2) in the future.

        - **Technician opportunity:** We are hiring a seagoing technician!  See the [job advert](../post/2025-03-08-technician). If this may be of interest to you, please email [Eleanor](mailto:eleanor.frajka@uni-hamburg.de).'
    design:
        columns: 2
  - block: slider
    content:
        slides:
        - title: 
          content: 
          align: center
          background:
            image:
              # Specify an image from `assets/media/`
              # or delete the image section to remove it
              filename: 230924_instruments-people.jpeg
              filters:
                brightness: 0.7
            position: right
            color: '#666'
    design:
        # Slide height is automatic unless you force a specific height (e.g. '400px')
        slide_height: ''
        # Make the slides full screen within the browser window?
        is_fullscreen: true
        # Automatically transition through slides?
        loop: false
        # Duration of transition between slides (in ms)
        interval: 2000
---


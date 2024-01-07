---
title: My page
type: landing

sections:
  - block: collection
    id: posts
    content:
      title: Resources
      subtitle: 'for EO group'
      text: 'Collection of links and how-tos for the group. <hr>'
      # Choose how many pages you would like to display (0 = all pages)
      count: 0
      # Filter on criteria
      filters:
        # The folders to display content from
        folders:
          - documents
        author: ""
        category: ""
        tag: ""
        publication_type: ""
        featured_only: false
        exclude_featured: false
        exclude_future: false
        exclude_past: false
      # Choose how many pages you would like to offset by
      # Useful if you wish to show the first item in the Featured widget
      offset: 0
      # Field to sort by, such as Date or Title
      sort_by: weight
      sort_ascending: true
    design:
      # Choose a listing view
      view: list
      columns: '2'
  - block: markdown
    content:
      title: Teaching
      subtitle: by the EO group
      text: 'The Experimental Oceanography group is part of the Institut für Meereskunde at the Universität Hamburg. We teach on the BSc in Geophysics/Oceanography and MSc in Ocean and Climate Physics. More information about the degree programs is available [here](https://www.ifm.uni-hamburg.de/en/education.html).

      Topics include:

      - Measurement methods. Instruments and platforms (in situ and remote sensing), and analysis techniques (programming) – lectures + training

      - Fieldwork training. Planning, experience, analysing data and presenting results – lectures, seminars + training

      - Rotating table and wind/wave tank – demonstrations + practical
      
      - Supervising student projects. Please contact us for information about projects supervised or co-supervised by the EO group. – research
      
      - Research cruises. Occasionally, by arrangement – practical'
    design:
      columns: 1
      spacing:
        # Customize the section spacing. Order is top, right, bottom, left.
        padding: ['20px', '0', '20px', '0']
  - block: accomplishments
    content:
      title: SuSe24
      subtitle: 'Courses led by EO group'
      text: ''
      # Date format: https://wowchemy.com/docs/customization/#date-format
      date_format: Jan 2006
      # Accomplishments.
      #   Add/remove as many `items` blocks below as you like.
      #   `title`, `organization`, and `date_start` are the required parameters.
      #   Leave other parameters empty if not required.
      #   Begin multi-line descriptions with YAML's `|2-` multi-line prefix.
      items:
        - title: MSc Seagoing Oceanography
          date_end: '2024-07-15'
          date_start: '2024-04-01'
          description: '- Instructor: Eleanor Frajka-Williams

          - Details: 6 credit points. Offered bi-annually.'
          icon: UHH
          organization: Universität Hamburg
          organization_url: https://www.ifm.uni-hamburg.de/en/education/master.html
          url: 'https://eleanorfrajka.com/teaching/seaocean/'
        - title: BSc Regional Oceanography
          date_end: '2024-07-15'
          date_start: '2024-04-01'
          description: '- Content: An introduction to oceans around the world, how they are described and typical processes.

          - Instructor: Eleanor Frajka-Williams'
          icon: UHH
          organization: Universität Hamburg
          organization_url: https://www.ifm.uni-hamburg.de/en/education/bachelor.html
          url: ''
        - title: BSc Seepraktikum
          date_start: '2024-04-01'
          date_end: '2024-07-15'
          description: '- Instructors: Martin Gade (lead), Eleanor Frajka-Williams, Niels Fuchs. 
          
          - Fieldwork course with excursion on the R/V Prandtl.  *Note that participation in Messmethoden & Fernerkundung is a prerequisite.*'
          icon: UHH
          organization: Universität Hamburg
          organization_url: https://www.ifm.uni-hamburg.de/en/education/bachelor.html
          author: "Martin Gade"
          url: ''
    design:
      # Choose how many columns the section has. Valid values: '1' or '2'.
      columns: '2'
      spacing:
        # Customize the section spacing. Order is top, right, bottom, left.
        padding: ['20px', '0', '20px', '0']
  - block: accomplishments
    content:
      title: WiSe23/24
      subtitle: 'Courses led by EO group'
      text: ''
      # Date format: https://wowchemy.com/docs/customization/#date-format
      date_format: Jan 2006
      # Accomplishments.
      #   Add/remove as many `items` blocks below as you like.
      #   `title`, `organization`, and `date_start` are the required parameters.
      #   Leave other parameters empty if not required.
      #   Begin multi-line descriptions with YAML's `|2-` multi-line prefix.
      items:
        - title: BSc Messmethoden & Fernerkundung
          date_end: '2024-01-31'
          date_start: '2023-10-01'
          description: '- Instructors: Martin Gade, Eleanor Frajka-Williams, Dirk Notz
          
          - Content: Observational methods including in situ instrumentation and satellite earth observation'
          icon: UHH
          organization: Universität Hamburg
          organization_url: https://www.ifm.uni-hamburg.de/en/education/bachelor.html
          url: 'https://wiki.cen.uni-hamburg.de/ifm/MessFern_V'
        - title: BSc Ocean exercises
          date_end: '2024-03-22'
          date_start: '2024-03-18'
          description: '- Instructors: Eleanor Frajka-Williams, Dagmar Hainbucher
          
          - Laboratory and field exercises for oceanography.  Taught as a 2-week block course during the semester break.'
          icon: UHH
          organization: Universität Hamburg
          organization_url: https://www.ifm.uni-hamburg.de/en/education/bachelor.html
          url: ''
    design:
      # Choose how many columns the section has. Valid values: '1' or '2'.
      columns: '2'  
      spacing:
        # Customize the section spacing. Order is top, right, bottom, left.
        padding: ['20px', '0', '20px', '0']
  - block: markdown
    content:
      title: Fieldwork gallery
      subtitle: ''
      text: |-
        {{< gallery album="terific1" >}}
        <br>
        [SEE ALL GALLERIES >](../galleries/)
    design:
      columns: '2'
---
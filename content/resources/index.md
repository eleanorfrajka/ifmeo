---
title: Resources
type: landing

sections:
  - block: collection
    id: posts
    content:
      title: Manual
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
  - block: collection
    id: posts
    content:
      title: Technology
      subtitle: 'in the EO group'
      text: 'Equipment and hardware used for research and teaching in the EU group. <hr>'
      # Choose how many pages you would like to display (0 = all pages)
      count: 0
      # Filter on criteria
      filters:
        # The folders to display content from
        folders:
          - technology
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
      title: Fieldwork gallery
      subtitle: ''
      text: |-
        {{< gallery album="terific1" >}}
        <br>
        [SEE ALL GALLERIES >](../galleries/)
    design:
      columns: '2'
---
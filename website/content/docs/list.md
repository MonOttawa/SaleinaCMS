---
title: List
group: widgets
---

The list widget allows you to create a repeatable item in the UI which saves as a list of widget values. map a user-provided string with a comma delimiter into a list. You can choose any widget as a child of a list widget—even other lists.

- **Name:** `list`
- **UI:** if `fields` is specified, field containing a repeatable child widget, with controls for adding, and deleting widgets; if unspecified, a text input for entering comma-separated values
- **Data type:** list of widget values
- **Options:**
  - `default`: if `fields` is specified, declare defaults on the child widgets; if not, you may specify a list of strings to populate the text field
  - `max`: limits the number of items in the list
  - `fields`: a nested list of multiple widget fields to be included in each repeatable iteration
- **Example** (`fields` not specified):

  ```yaml
  - label: "Tags"
    name: "tags"
    widget: "list"
    default: ["news"]
  ```

- **Example** (with `fields`):

  ```yaml
  - label: "Testimonials"
    name: "testimonials"
    widget: "list"
    fields:
      - {label: Quote, name: quote, widget: string, default: "Everything is awesome!"}
      - label: Author
        name: author
        widget: object
        fields:
          - {label: Name, name: name, widget: string, default: "Emmet"}
          - {label: Avatar, name: avatar, widget: image, default: "/img/emmet.jpg"}
  ```

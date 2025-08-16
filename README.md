# nice_view_module
## Usage
> [!WARNING]
> This is still in development

This is a custom module for the nice-view in my 6rows corne

To use this module, first add it to your `config/west.yml` by adding a new entry to remotes and projects:

```yml
manifest:
  defaults:
    revision: v0.3
  remotes:
    - name: zmkfirmware
      url-base: https://github.com/zmkfirmware
    - name: mArcio-Lmano                         #new entry
      url-base: https://github.com/mArcio-Lmano  #new entry
  projects:
    - name: zmk
      remote: zmkfirmware
      import: app/west.yml
    - name: nice_view_module   #new entry
      remote: mArcio-Lmano     #new entry
      revision: New/animation  #new entry
  self:
    path: config
```

Now simply swap out the default nice_view shield on the board for the custom one in your `build.yaml` file.

```yml
---
include:
  - board: nice_nano_v2
    shield: corne_left nice_view_adapter  nice_view_custom #custom shield
  - board: nice_nano_v2
    shield: corne_right nice_view_adapter nice_view_custom #custom shield
```

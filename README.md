# Paper Purple

A low-contrast theme for NeoVim, based on
[nvim-grey](https://github.com/yorickpeterse/nvim-grey) and written in Lua

PaperPurple is a continuation of the goal of making a light theme that's easy on the
eyes, and not distracting by introducing many colors. The most notable
difference compared to Grey or Paper is that Keywords are a dark purple. Hence the (incredibly creative) name.

Like Paper, this theme is best used on a low brightness display, with a color
temperature of <5500K. During the day I use a color temperature of 5200K, while
at night the temperature is set to 3800K. This theme probably won't look so good
when using the common display temperature of 6500K.

# Screenshots
<img width="1888" height="1072" alt="image" src="https://github.com/user-attachments/assets/30276c1c-d32e-4dc6-bbd3-cb237403b5f6" />

# Requirements

* NeoVim 0.7.0 or newer (due to the use of `nvim_set_hl()`)
* true-color support

For best results use `set laststatus=3` (introduced in NeoVim 0.8), as the theme
is designed with this setting in mind.

# Installation

## Vim Plug

    Plug 'arompr/paper-purple.nvim'

## Lazy

    return { "arompr/paper-purple.nvim" }

# Telescope extension

An extension for Telescope is included, providing a layout strategy called
"paper_purple". It's recommended that Telescope users use this layout, as the theme
applies highlights with this layout in mind. To enable, configure Telescope like
so:

```lua
require('telescope').setup({
  defaults = {
    -- These three settings are optional, but recommended.
    prompt_prefix = '',
    entry_prefix = ' ',
    selection_caret = ' ',

    -- This is the important part: without this, Telescope windows will look a
    -- bit odd due to how borders are highlighted.
    layout_strategy = 'paper_purple',
    layout_config = {
     -- The extension supports both "top" and "bottom" for the prompt.
      prompt_position = 'top',

      -- You can adjust these settings to your liking.
      width = 0.6,
      height = 0.5,
      preview_width = 0.6,
    },
  }
})

telescope.load_extension('paper_purple')
```

# License

All source code in this repository is licensed under the Mozilla Public License
version 2.0, unless stated otherwise. A copy of this license can be found in the
file "LICENSE".

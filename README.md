# in-and-out.nvim

<p align="center">
  <img src="https://github.com/ysmb-wtsg/in-and-out.nvim/assets/85178719/cdfa26ec-6302-4413-b586-781ece8e99c0" width="70%" height="400px" object-fit="cover">
</p>

`in-and-out` is a Neovim plugin designed to quickly navigate in and out of surrounding characters like quotes (`"`, `'`), parentheses (`(`, `)`), curly braces (`{`, `}`), and square brackets (`[`, `]`).

![demo](https://github.com/ysmb-wtsg/in-and-out.nvim/assets/85178719/9b641329-bd71-4931-8ad8-c1051641ccd2)

## Installation

Using `lazy` or `packer`:

```lua
{
	"ysmb-wtsg/in-and-out.nvim",
	config = function()
		vim.keymap.set("i", "<C-CR>", function()
			require("in-and-out").in_and_out()
		end
	end,
}
```

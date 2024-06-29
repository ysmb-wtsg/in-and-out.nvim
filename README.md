# in-and-out.nvim

<p align="center">
  <img src="https://github.com/ysmb-wtsg/in-and-out.nvim/assets/85178719/cdfa26ec-6302-4413-b586-781ece8e99c0" width="70%" height="400px" object-fit="cover">
</p>

`in-and-out` is a Neovim plugin designed to quickly navigate in and out of surrounding characters like quotes (`"`, `'`), parentheses (`(`, `)`), curly braces (`{`, `}`), square brackets (`[`, `]`), and backticks (<code>`</code>).

![demo](https://github.com/ysmb-wtsg/in-and-out.nvim/assets/85178719/9b641329-bd71-4931-8ad8-c1051641ccd2)

## Installation

Use your favorite package manager. For example, using `lazy`:

```lua
{
	"ysmb-wtsg/in-and-out.nvim",
	keys = {
		{
			"<C-CR>",
			function()
				require("in-and-out").in_and_out()
			end,
			mode = "i"
                },
	},
}
```

## Configuration

By default, this plugin will jump into and out of the following surrounding characters:

```lua
{ '"', "'", "(", ")", "{", "}", "[", "]", "`" }
```

If you are happy with this list of targets, you don't need to do any configuration, and you don't need to call `setup`.

On the other hand, if you want to add to the list of targets or replace it altogether, use the plugin's `setup` method. To add targets, pass `setup` an options table containing a sublist named `additional_targets`. To replace the original targets list entirely, pass `setup` an options table with a sublist called `targets`.

Note: you cannot use both the `targets` and the `additional_targets` sublists at the same time. If you try, the plugin will apply `targets` and ignore `additional_targets`.

See the examples below.

Using `lazy` to add smart quotes as a target:

```lua
{
	"ysmb-wtsg/in-and-out.nvim",
	keys = {
		{
			"<C-CR>",
			function()
				require("in-and-out").in_and_out()
			end,
			mode = "i"
                },
	},
	opts = { additional_targets = { "“", "”" } },
}
```

Manual `require` to reset the targets altogether:

```lua
require("in-and-out.nvim").setup({
	targets = { "(", ")", "[", "]" }
})
```

## Mapping

By default, the plugin does not set any mapping. You can set one through your plugin manager (if it supports setting mappings) or manually.

Using `lazy`:

```lua
{
	"ysmb-wtsg/in-and-out.nvim",
        keys = {
                {
                        "<C-CR>",
                        function()
                                require("in-and-out").in_and_out()
                        end,
                        mode = "i"
                },
        },
	opts = { additional_targets = { "“", "”" } },
}
```

Manually:

```lua
vim.keymap.set("i", "<C-CR>", function() require("in-and-out").in_and_out()
end)
```

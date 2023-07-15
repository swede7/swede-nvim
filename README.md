# Swede nvim configuration

## Install

Add lsp configuration:

```lua
local swedePath = '/ABSOLUTE/PATH/TO/swede-cli-1.0-SNAPSHOT.jar'

require('lspconfig.configs').swede = {
  default_config = {
    name = 'swede',
    cmd = { 'java', '-jar',  swedePath, 'lsp', '--stdio'},
    filetypes = {'swede', 'speca'},
    single_file_support = true,
    root_dir = function() return vim.fn.getcwd() end;
  }
}

require('lspconfig').swede.setup{}
```

Register filetype:

```lua
vim.filetype.add({
  extension = {
    swede = 'swede',
  },
})
```

## Debug

```lua
vim.lsp.set_log_level("debug")
```

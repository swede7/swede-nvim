# Swede nvim configuration

## Install

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

ftdetect/swede.vim

```vim
autocmd BufRead,BufNewFile *.swede setfiletype swede
```

## Debug

```lua
vim.lsp.set_log_level("debug")
```

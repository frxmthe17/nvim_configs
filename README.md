# nvim_configs
theme:
return {
  {
    "Mofiqul/vscode.nvim",
    lazy = false,
    priority = 1000,
    config = function()
      vim.cmd("colorscheme vscode")
    end,
  },
}

lsp set via :MasonInstall
-- typescript-server-language
-- gopls

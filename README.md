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


autosave:
-- Автосохранение при выходе из режима вставки или смене фокуса
vim.api.nvim_create_autocmd({ "InsertLeave", "TextChanged", "FocusLost" }, {
    pattern = "*",
    nested = true,
    callback = function()
        -- Проверяем, что буфер можно редактировать и это обычный файл
        if vim.bo.modified and vim.bo.buftype == "" and vim.fn.filereadable(vim.fn.expand("%")) == 1 then
            vim.cmd('silent! write')
        end
    end,
})

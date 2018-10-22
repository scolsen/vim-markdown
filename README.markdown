# Vim Markdown runtime files

This is the development version of Vim's included syntax highlighting and
filetype plugins for Markdown.  Generally you don't need to install these if
you are running a recent version of Vim.

One difference between this repository and the upstream files in Vim is that
the former forces `*.md` as Markdown, while the latter detects it as Modula-2,
with an exception for `README.md`.  If you'd like to force Markdown without
installing from this repository, add the following to your vimrc:

    autocmd BufNewFile,BufReadPost *.md set filetype=markdown

## Configuration

### Fenced Codeblock Highlighting

To enable fenced code block syntax highlighting in your markdown
documents, add the following to your `.vimrc`:

    let g:markdown_fenced_languages = ['html', 'python', 'bash=sh']

**Note**: The fenced language names must be valid names of syntax files in vim's `syntax` folder. For example: `syntax/ruby.vim`.

### Syntax Concealment

To disable markdown syntax concealing, add the following to your `.vimrc`:

    let g:markdown_syntax_conceal = 0

### Highlighting Synchronization

Syntax highlighting is synchronized in 50 lines. This may cause collapsed
highlighting on large fenced code blocks.
In that case, set `g:markdown_minlines` to a larger value in your `.vimrc`:

    let g:markdown_minlines = 100

**Note**: Setting `g:markdown_minlines` to a value that is too large value may cause poor highlighting performance.

### Folding

To enable folding, add the following to your `.vimrc`:

    let g:markdown_folding = 1

## License

Copyright © Tim Pope.  Distributed under the same terms as Vim itself.
See `:help license`.

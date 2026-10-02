# Laravel Kanban

> [!WARNING]
> This package is no longer maintained. The kanban board, `vendor/bin/kanban`, the `/kanban` page and the Claude Code
> agents are part of [petar-spasic/laravel-house](https://github.com/petar-spasic/laravel-house) from v0.5.0 on.

The two packages conflict, so a project moves in one step. Stop any running agents, then run this in one shell call
(leave out `vendor/bin/kanban doctor --fix` when the project has no board):

```shell
composer remove --dev petar-spasic/laravel-kanban && composer require --dev petar-spasic/laravel-house -W && vendor/bin/kanban doctor --fix && php artisan boost:update
```

`doctor --fix` moves what this package stored (`.git/laravel-kanban`, the markers, the git hooks path, the compose
deploy-key path) to the new names. Then restart Claude Code and run `/implement-kanban`, which finishes the move.
The [laravel-house README](https://github.com/petar-spasic/laravel-house#the-kanban-board) covers the board.

## License

Laravel Kanban is open-sourced software licensed under the [MIT license](LICENSE).

> 插件推荐

`git sudo extract tmux zsh-autosuggestions zsh-syntax-highlighting`

* sudo 双击esc 快速在命令前加sudo 
* extract 解压命令 需安装tar,zip,unrar等命令配合使用，不用单独调每一个命令，同意使用这个解压

* [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md)

* [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md)

* tmux

  需要安装[tmux](https://tmux.github.io/)配合使用

| Alias  | Command                | Description                                              |
| ------ | ---------------------- | -------------------------------------------------------- |
| `ta`   | tmux attach -t         | Attach new tmux session to already running named session |
| `tad`  | tmux attach -d -t      | Detach named tmux session                                |
| `ts`   | tmux new-session -s    | Create a new named tmux session                          |
| `tl`   | tmux list-sessions     | Displays a list of running tmux sessions                 |
| `tksv` | tmux kill-server       | Terminate all running tmux sessions                      |
| `tkss` | tmux kill-session -t   | Terminate named running tmux session                     |
| `tmux` | `_zsh_tmux_plugin_run` | Start a new tmux session                                 |


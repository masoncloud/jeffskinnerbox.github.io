An integrated development environment (IDE) is a programming environment
that has been packaged as an application program,
typically consisting of a code editor, a compiler, a debugger,
and a graphical user interface (GUI) builder.

* [vim][14] highly customizable editor.
* [Terminator][01]
is a terminal emulator released under General Public License
and is available for GNU/Linux Platform.
The application program lets you use multiple splits and resized terminals,
all at once on a single screen.
The [configuration file][02] `~/.config/terminator/config`
is used to control options not in gnome-terminal `gconf` profiles, or override `gconf` settings.
    * [Getting the most out of Terminator][20]
* [iTerm2][09] is a replacement for the Mac's native Terminal.
As of this writing, it works only Macs, and like Terminator, does split screens, etc.
* [tmux][10] is a terminal multiplexer that allows us to create sessions
that act roughly like terminal windows, create windows that act like tabs,
and create panes that let us split tmux windows horizontally and vertically.
Since multiple people can connect to a tmux session at a time it gives us
the ability to pair on remote machines or even from separate locations.
These sites may  help in learning tmux:
    * [Intro to Tmux][16]
    * [A tmux Crash Course][13]
    * [Beginner’s Guide to Tmux: Recommended Configuration, Plugins and Navigation Demo][15]
    * TMUX – The Terminal Multiplexer, [Part 1][18] amd [Part 2][19]
* [Screen][04] is a full-screen window manager that multiplexes a physical terminal
between several processes, typically interactive shells.
Each virtual terminal provides the functions of the DEC VT100 terminal and, in addition,
several control functions from the ANSI X3.64 (ISO 6429) and ISO 2022 standards
(e.g., insert/delete line and support for multiple character sets).
* [vimux = vim + tmux][05] is a integration of these two tools via a [`vim` plugin][06].
Of course this is one of many ways to do this integration.
    * [Build an IDE with tmux and vim][07]
    * [Vim and Tmux on your Mac][08]
See [vim + tmux - OMG!Code][03] for a good video on how these two tools can work together.
* [iTerm2  tmux][11] is an integration to [overcome some of the short comings][12]
of iTerm2 window splits.
    * [Tmuxintegration][17]



[01]:http://gnometerminator.blogspot.com/?view=flipcard
[02]:http://manpages.ubuntu.com/manpages/jaunty/man5/terminator_config.5.html
[03]:https://www.youtube.com/watch?v=5r6yzFEXajQ
[04]:https://www.linode.com/docs/networking/ssh/using-gnu-screen-to-manage-persistent-terminal-sessions
[05]:https://www.braintreepayments.com/blog/vimux-simple-vim-and-tmux-integration/
[06]:https://github.com/benmills/vimux
[07]:http://alexyoung.org/2011/12/19/build-an-ide-with-tmux-and-vim/
[08]:http://fideloper.com/mac-vim-tmux
[09]:https://www.iterm2.com/
[10]:https://danielmiessler.com/study/tmux/
[11]:http://www.huyng.com/posts/productivity-boost-with-tmux-iterm2-workspaces/
[12]:http://superuser.com/questions/398735/difference-between-tmux-and-shell-split-options-on-iterm2
[13]:https://robots.thoughtbot.com/a-tmux-crash-course
[14]:http://vim.wikia.com/wiki/Tutorial
[15]:https://www.codementor.io/tmux/tutorial/beginners-guide-to-tmux-navigating-and-configuring-your-tmux
[16]:http://code.tutsplus.com/tutorials/intro-to-tmux--net-33889
[17]:https://gitlab.com/gnachman/iterm2/wikis/TmuxIntegration
[18]:http://blog.hawkhost.com/2010/06/28/tmux-the-terminal-multiplexer/
[19]:http://blog.hawkhost.com/2010/07/02/tmux-%E2%80%93-the-terminal-multiplexer-part-2/
[20]:http://blog.al4.co.nz/2011/05/getting-the-most-out-of-terminator/
[21]:
[22]:
[23]:
[24]:
[25]:
[26]:
[27]:
[28]:
[29]:
[30]:

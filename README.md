# myconfig

### ~/.vimrc

```sh
set nocompatible              " be iMproved, required
filetype off                  " required

" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
" alternatively, pass a path where Vundle should install plugins
"call vundle#begin('~/some/path/here')

" let Vundle manage Vundle, required
Plugin 'VundleVim/Vundle.vim'

" The following are examples of different formats supported.
" Keep Plugin commands between vundle#begin/end.
" plugin on GitHub repo
Plugin 'tpope/vim-fugitive'
" plugin from http://vim-scripts.org/vim/scripts.html
" Plugin 'L9'
" Git plugin not hosted on GitHub
Plugin 'git://git.wincent.com/command-t.git'
" git repos on your local machine (i.e. when working on your own plugin)
" Plugin 'file:///home/gmarik/path/to/plugin'
" The sparkup vim script is in a subdirectory of this repo called vim.
" Pass the path to set the runtimepath properly.
Plugin 'rstacruz/sparkup', {'rtp': 'vim/'}
" Install L9 and avoid a Naming conflict if you've already installed a
" different version somewhere else.
" Plugin 'ascenator/L9', {'name': 'newL9'}

Plugin 'flazz/vim-colorschemes'
Plugin 'tpope/vim-surround'
Plugin 'xolox/vim-colorscheme-switcher'
Plugin 'xolox/vim-misc'

" All of your Plugins must be added before the following line
call vundle#end()            " required
filetype plugin indent on    " required
" To ignore plugin indent changes, instead use:
"filetype plugin on
"
" Brief help
" :PluginList       - lists configured plugins
" :PluginInstall    - installs plugins; append `!` to update or just :PluginUpdate
" :PluginSearch foo - searches for foo; append `!` to refresh local cache
" :PluginClean      - confirms removal of unused plugins; append `!` to auto-approve removal
"
" see :h vundle for more details or wiki for FAQ
" Put your non-Plugin stuff after this line




" Настройки табов для Python, согласно рекоммендациям
set tabstop=4 
set shiftwidth=4
set smarttab
set expandtab "Ставим табы пробелами
set softtabstop=4 "4 пробела в табе
" Автоотступ
set autoindent
" Подсвечиваем все что можно подсвечивать
let python_highlight_all = 1
" Включаем 256 цветов в терминале, мы ведь работаем из иксов?
" Нужно во многих терминалах, например в gnome-terminal
set t_Co=256

" Перед сохранением вырезаем пробелы на концах (только в .py файлах)
autocmd BufWritePre *.py normal m`:%s/\s\+$//e ``
" В .py файлах включаем умные отступы после ключевых слов
autocmd BufRead *.py set smartindent cinwords=if,elif,else,for,while,try,except,finally,def,class

syntax on "Включить подсветку синтаксиса

" set nu "Включаем нумерацию строк
set mousehide "Спрятать курсор мыши когда набираем текст
set mouse=a "Включить поддержку мыши
set termencoding=utf-8 "Кодировка терминала
set novisualbell "Не мигать 
set t_vb= "Не пищать! (Опции 'не портить текст', к сожалению, нету)
" Удобное поведение backspace
set backspace=indent,eol,start whichwrap+=<,>,[,]
" Вырубаем черточки на табах
set showtabline=1

" Переносим на другую строчку, разрываем строки
set wrap
set linebreak

" Вырубаем .swp и ~ (резервные) файлы
set nobackup
set noswapfile
set encoding=utf-8 " Кодировка файлов по умолчанию
set fileencodings=utf8,cp1251

set clipboard=unnamed
set ruler

set hidden
nnoremap <C-N> :bnext<CR>
nnoremap <C-P> :bprev<CR>

" Выключаем звук в Vim
set visualbell t_vb=

"Переключение табов по CMD+number для MacVim
if has("gui_macvim")
  " Press Ctrl-Tab to switch between open tabs (like browser tabs) to 
  " the right side. Ctrl-Shift-Tab goes the other way.
  noremap <C-Tab> :tabnext<CR>
  noremap <C-S-Tab> :tabprev<CR>

  " Switch to specific tab numbers with Command-number
  noremap <D-1> :tabn 1<CR>
  noremap <D-2> :tabn 2<CR>
  noremap <D-3> :tabn 3<CR>
  noremap <D-4> :tabn 4<CR>
  noremap <D-5> :tabn 5<CR>
  noremap <D-6> :tabn 6<CR>
  noremap <D-7> :tabn 7<CR>
  noremap <D-8> :tabn 8<CR>
  noremap <D-9> :tabn 9<CR>
  " Command-0 goes to the last tab
  noremap <D-0> :tablast<CR>
endif

set guifont=Monaco:h18
colorscheme trivial256
```


### ~/.zshrc

```sh
# If you come from bash you might have to change your $PATH.
# export PATH=$HOME/bin:/usr/local/bin:$PATH

# Path to your oh-my-zsh installation.
export ZSH="/Users/usrsem/.oh-my-zsh"

# Set name of the theme to load --- if set to "random", it will
# load a random theme each time oh-my-zsh is loaded, in which case,
# to know which specific one was loaded, run: echo $RANDOM_THEME
# See https://github.com/ohmyzsh/ohmyzsh/wiki/Themes
# ZSH_THEME="frontcube"
# ZSH_THEME="refined"
# ZSH_THEME="muse"
ZSH_THEME="arrow"

# Set list of themes to pick from when loading at random
# Setting this variable when ZSH_THEME=random will cause zsh to load
# a theme from this variable instead of looking in $ZSH/themes/
# If set to an empty array, this variable will have no effect.
# ZSH_THEME_RANDOM_CANDIDATES=( "robbyrussell" "agnoster" )

# Uncomment the following line to use case-sensitive completion.
# CASE_SENSITIVE="true"

# Uncomment the following line to use hyphen-insensitive completion.
# Case-sensitive completion must be off. _ and - will be interchangeable.
# HYPHEN_INSENSITIVE="true"

# Uncomment the following line to disable bi-weekly auto-update checks.
# DISABLE_AUTO_UPDATE="true"

# Uncomment the following line to automatically update without prompting.
# DISABLE_UPDATE_PROMPT="true"

# Uncomment the following line to change how often to auto-update (in days).
# export UPDATE_ZSH_DAYS=13

# Uncomment the following line if pasting URLs and other text is messed up.
# DISABLE_MAGIC_FUNCTIONS="true"

# Uncomment the following line to disable colors in ls.
# DISABLE_LS_COLORS="true"

# Uncomment the following line to disable auto-setting terminal title.
# DISABLE_AUTO_TITLE="true"

# Uncomment the following line to enable command auto-correction.
# ENABLE_CORRECTION="true"

# Uncomment the following line to display red dots whilst waiting for completion.
# COMPLETION_WAITING_DOTS="true"

# Uncomment the following line if you want to disable marking untracked files
# under VCS as dirty. This makes repository status check for large repositories
# much, much faster.
# DISABLE_UNTRACKED_FILES_DIRTY="true"

# Uncomment the following line if you want to change the command execution time
# stamp shown in the history command output.
# You can set one of the optional three formats:
# "mm/dd/yyyy"|"dd.mm.yyyy"|"yyyy-mm-dd"
# or set a custom format using the strftime function format specifications,
# see 'man strftime' for details.
# HIST_STAMPS="mm/dd/yyyy"

# Would you like to use another custom folder than $ZSH/custom?
# ZSH_CUSTOM=/path/to/new-custom-folder

# Which plugins would you like to load?
# Standard plugins can be found in $ZSH/plugins/
# Custom plugins may be added to $ZSH_CUSTOM/plugins/
# Example format: plugins=(rails git textmate ruby lighthouse)
# Add wisely, as too many plugins slow down shell startup.
# plugins=(git)

source $ZSH/oh-my-zsh.sh

# User configuration

# export MANPATH="/usr/local/man:$MANPATH"

# You may need to manually set your language environment
# export LANG=en_US.UTF-8

# Preferred editor for local and remote sessions
# if [[ -n $SSH_CONNECTION ]]; then
#   export EDITOR='vim'
# else
#   export EDITOR='mvim'
# fi

# Compilation flags
# export ARCHFLAGS="-arch x86_64"

# Set personal aliases, overriding those provided by oh-my-zsh libs,
# plugins, and themes. Aliases can be placed here, though oh-my-zsh
# users are encouraged to define aliases within the ZSH_CUSTOM folder.
# For a full list of active aliases, run `alias`.
#
# Example aliases
# alias zshconfig="mate ~/.zshrc"
# alias ohmyzsh="mate ~/.oh-my-zsh"
alias python=python3
```

### .tmux.conf

```sh
# : << EOF
# https://github.com/gpakosz/.tmux
# (‑●‑●)> dual licensed under the WTFPL v2 license and the MIT license,
#         without any warranty.
#         Copyright 2012— Gregory Pakosz (@gpakosz).
# /!\ do not edit this file
#     instead, override settings in ~/.tmux.conf.local, see README.md


# -- general -------------------------------------------------------------------

set -g default-terminal "screen-256color" # colors!
setw -g xterm-keys on
set -s escape-time 10                     # faster command sequences
set -sg repeat-time 600                   # increase repeat timeout
set -s focus-events on

set -g prefix2 C-a                        # GNU-Screen compatible prefix
bind C-a send-prefix -2

set -q -g status-utf8 on                  # expect UTF-8 (tmux < 2.2)
setw -q -g utf8 on

set -g history-limit 5000                 # boost history

# edit configuration
bind e new-window -n "~/.tmux.conf.local" "sh -c '\${EDITOR:-vim} ~/.tmux.conf.local && tmux source ~/.tmux.conf && tmux display \"~/.tmux.conf sourced\"'"

# reload configuration
bind r source-file ~/.tmux.conf \; display '~/.tmux.conf sourced'


# -- display -------------------------------------------------------------------

set -g base-index 1           # start windows numbering at 1
setw -g pane-base-index 1     # make pane numbering consistent with windows

setw -g automatic-rename on   # rename window to reflect current program
set -g renumber-windows on    # renumber windows when a window is closed

set -g set-titles on          # set terminal title

set -g display-panes-time 800 # slightly longer pane indicators display time
set -g display-time 1000      # slightly longer status messages display time

set -g status-interval 10     # redraw status line every 10 seconds

# clear both screen and history
bind -n C-l send-keys C-l \; run 'sleep 0.1' \; clear-history

# activity
set -g monitor-activity on
set -g visual-activity off


# -- navigation ----------------------------------------------------------------

# create session
bind C-c new-session

# find session
bind C-f command-prompt -p find-session 'switch-client -t %%'

# split current window horizontally
bind - split-window -v
# split current window vertically
bind _ split-window -h

# pane navigation
bind -r h select-pane -L  # move left
bind -r j select-pane -D  # move down
bind -r k select-pane -U  # move up
bind -r l select-pane -R  # move right
bind > swap-pane -D       # swap current pane with the next one
bind < swap-pane -U       # swap current pane with the previous one

# maximize current pane
bind + run 'cut -c3- ~/.tmux.conf | sh -s _maximize_pane "#{session_name}" #D'

# pane resizing
bind -r H resize-pane -L 2
bind -r J resize-pane -D 2
bind -r K resize-pane -U 2
bind -r L resize-pane -R 2

# window navigation
unbind n
unbind p
bind -r C-h previous-window # select previous window
bind -r C-l next-window     # select next window
bind Tab last-window        # move to last active window

# toggle mouse
bind m run "cut -c3- ~/.tmux.conf | sh -s _toggle_mouse"


# -- urlview -------------------------------------------------------------------

bind U run "cut -c3- ~/.tmux.conf | sh -s _urlview #{pane_id}"


# -- facebook pathpicker -------------------------------------------------------

bind F run "cut -c3- ~/.tmux.conf | sh -s _fpp #{pane_id}"


# -- list choice (tmux < 2.4) --------------------------------------------------

# vi-choice is gone in tmux >= 2.4
run -b 'tmux bind -t vi-choice h tree-collapse 2> /dev/null || true'
run -b 'tmux bind -t vi-choice l tree-expand 2> /dev/null || true'
run -b 'tmux bind -t vi-choice K start-of-list 2> /dev/null || true'
run -b 'tmux bind -t vi-choice J end-of-list 2> /dev/null || true'
run -b 'tmux bind -t vi-choice H tree-collapse-all 2> /dev/null || true'
run -b 'tmux bind -t vi-choice L tree-expand-all 2> /dev/null || true'
run -b 'tmux bind -t vi-choice Escape cancel 2> /dev/null || true'


# -- edit mode (tmux < 2.4) ----------------------------------------------------

# vi-edit is gone in tmux >= 2.4
run -b 'tmux bind -ct vi-edit H start-of-line 2> /dev/null || true'
run -b 'tmux bind -ct vi-edit L end-of-line 2> /dev/null || true'
run -b 'tmux bind -ct vi-edit q cancel 2> /dev/null || true'
run -b 'tmux bind -ct vi-edit Escape cancel 2> /dev/null || true'


# -- copy mode -----------------------------------------------------------------

bind Enter copy-mode # enter copy mode

run -b 'tmux bind -t vi-copy v begin-selection 2> /dev/null || true'
run -b 'tmux bind -T copy-mode-vi v send -X begin-selection 2> /dev/null || true'
run -b 'tmux bind -t vi-copy C-v rectangle-toggle 2> /dev/null || true'
run -b 'tmux bind -T copy-mode-vi C-v send -X rectangle-toggle 2> /dev/null || true'
run -b 'tmux bind -t vi-copy y copy-selection 2> /dev/null || true'
run -b 'tmux bind -T copy-mode-vi y send -X copy-selection-and-cancel 2> /dev/null || true'
run -b 'tmux bind -t vi-copy Escape cancel 2> /dev/null || true'
run -b 'tmux bind -T copy-mode-vi Escape send -X cancel 2> /dev/null || true'
run -b 'tmux bind -t vi-copy H start-of-line 2> /dev/null || true'
run -b 'tmux bind -T copy-mode-vi H send -X start-of-line 2> /dev/null || true'
run -b 'tmux bind -t vi-copy L end-of-line 2> /dev/null || true'
run -b 'tmux bind -T copy-mode-vi L send -X end-of-line 2> /dev/null || true'

# copy to macOS clipboard
if -b 'command -v pbcopy > /dev/null 2>&1' 'bind y run -b "tmux save-buffer - | pbcopy"'
if -b 'command -v reattach-to-user-namespace > /dev/null 2>&1' 'bind y run -b "tmux save-buffer - | reattach-to-user-namespace pbcopy"'
# copy to X11 clipboard
if -b 'command -v xsel > /dev/null 2>&1' 'bind y run -b "tmux save-buffer - | xsel -i -b"'
if -b '! command -v xsel > /dev/null 2>&1 && command -v xclip > /dev/null 2>&1' 'bind y run -b "tmux save-buffer - | xclip -i -selection clipboard >/dev/null 2>&1"'
# copy to Windows clipboard
if -b 'command -v clip.exe > /dev/null 2>&1' 'bind y run -b "tmux save-buffer - | clip.exe"'
if -b '[ -c /dev/clipboard ]' 'bind y run -b "tmux save-buffer - > /dev/clipboard"'


# -- buffers -------------------------------------------------------------------

bind b list-buffers  # list paste buffers
bind p paste-buffer  # paste from the top paste buffer
bind P choose-buffer # choose which buffer to paste from


# -- user defined overrides ----------------------------------------------------

if '[ -f ~/.tmux.conf.local ]' 'source ~/.tmux.conf.local'


# -- 8< ------------------------------------------------------------------------

run 'cut -c3- ~/.tmux.conf | sh -s _apply_configuration'
run -b '[ -z "#{window_active}" ] && [ -z "#{version}" ] && tmux set display-time 3000 \; display "This configuration will soon require tmux >= 2.4" \; set -u display-time || true'


# EOF
#
# # exit the script if any statement returns a non-true return value
# set -e
#
# unset GREP_OPTIONS
# export LC_NUMERIC=C
#
# if ! printf '' | sed -E 's///' 2>/dev/null; then
#   if printf '' | sed -r 's///' 2>/dev/null; then
#     sed () {
#       n=$#; while [ "$n" -gt 0 ]; do arg=$1; shift; case $arg in -E*) arg=-r${arg#-E};; esac; set -- "$@" "$arg"; n=$(( n - 1 )); done
#       command sed "$@"
#     }
#   fi
# fi
#
# _uname_s=$(uname -s)
#
# _is_enabled() {
#   [ x"$1" = x"true" ] || [ x"$1" = x"yes" ] || [ x"$1" = x"enabled" ] || [ x"$1" = x"1" ]
# }
#
# _circled() {
#   circled_digits='⓪ ① ② ③ ④ ⑤ ⑥ ⑦ ⑧ ⑨ ⑩ ⑪ ⑫ ⑬ ⑭ ⑮ ⑯ ⑰ ⑱ ⑲ ⑳'
#   if [ "$1" -le 20 ] 2>/dev/null; then
#     i=$(( $1 + 1 ))
#     eval set -- "$circled_digits"
#     eval echo "\${$i}"
#   else
#     echo "$1"
#   fi
# }
#
# _decode_unicode_escapes() {
#   printf '%s' "$*" | perl -CS -pe 's/(\\u([0-9A-Fa-f]{1,4})|\\U([0-9A-Fa-f]{1,8}))/chr(hex($2.$3))/eg' 2>/dev/null
# }
#
# if command -v pkill > /dev/null 2>&1; then
#   _pkillf() {
#     pkill -f "$@" || true
#   }
# else
#   case "$_uname_s" in
#     *CYGWIN*)
#       _pkillf() {
#         while IFS= read -r pid; do
#           kill "$pid" || true
#         done  << EOF
# $(grep -Eao "$@" /proc/*/cmdline | xargs -0 | sed -E -n 's,/proc/([0-9]+)/.+$,\1,pg')
# EOF
#       }
#       ;;
#     *)
#       _pkillf() {
#         while IFS= read -r pid; do
#           kill "$pid" || true
#         done  << EOF
# $(ps -x -o pid= -o command= | grep -E "$@" | cut -d' ' -f1)
# EOF
#       }
#       ;;
#   esac
# fi
#
# _maximize_pane() {
#   current_session=${1:-$(tmux display -p '#{session_name}')}
#   current_pane=${2:-$(tmux display -p '#{pane_id}')}
#
#   dead_panes=$(tmux list-panes -s -t "$current_session" -F '#{pane_dead} #{pane_id} #{pane_start_command}' | grep -E -o '^1 %.+maximized.+$' || true)
#   restore=$(echo "$dead_panes" | sed -n -E -e "s/^1 $current_pane .+maximized.+'(%[0-9]+)'$/tmux swap-pane -s \1 -t $current_pane \; kill-pane -t $current_pane/p" -e "s/^1 (%[0-9]+) .+maximized.+'$current_pane'$/tmux swap-pane -s \1 -t $current_pane \; kill-pane -t \1/p" )
#
#   if [ -z "$restore" ]; then
#     [ "$(tmux list-panes -t "$current_session:" | wc -l | sed 's/^ *//g')" -eq 1 ] && tmux display "Can't maximize with only one pane" && return
#     window=$(tmux new-window -t "$current_session:" -P "exec maximized... 2> /dev/null & tmux setw -t \"$current_session:\" remain-on-exit on; printf \"Pane has been maximized, press <prefix>+ to restore. %s\" '$current_pane'")
#     window=${window%.*}
#
#     retry=1000
#     while [ x"$(tmux list-panes -t "$window" -F '#{session_name}:#{window_index} #{pane_dead}' 2>/dev/null)" != x"$window 1" ] && [ "$retry" -ne 0 ]; do
#       sleep 0.1
#       retry=$((retry - 1))
#     done
#     if [ "$retry" -eq 0 ]; then
#       tmux display 'Unable to maximize pane'
#     fi
#
#     new_pane=$(tmux display -t "$window" -p '#{pane_id}')
#     tmux setw -t "$window" remain-on-exit off \; swap-pane -s "$current_pane" -t "$new_pane"
#   else
#     $restore || tmux kill-pane
#   fi
# }
#
# _toggle_mouse() {
#   old=$(tmux show -gv mouse)
#   new=""
#
#   if [ "$old" = "on" ]; then
#     new="off"
#   else
#     new="on"
#   fi
#
#   tmux set -g mouse $new \;\
#        display "mouse: $new"
# }
#
# _battery_info() {
#   count=0
#   charge=0
#   case "$_uname_s" in
#     *Darwin*)
#       while IFS= read -r line; do
#         [ -z "$line" ] && continue
#         discharging=$(printf '%s' "$line" | grep -qi "discharging" && echo "true" || echo "false")
#         percentage=$(printf '%s' "$line" | grep -E -o '[0-9]+%')
#         charge=$(awk -v charge="$charge" -v percentage="${percentage%%%}" 'BEGIN { print charge + percentage / 100 }')
#         count=$((count + 1))
#       done  << EOF
# $(pmset -g batt | grep 'InternalBattery')
# EOF
#       ;;
#     *Linux*)
#       while IFS= read -r batpath; do
#         [ -z "$batpath" ] && continue
#         grep -i -q device "$batpath/scope" 2> /dev/null && continue
#
#         discharging=$(grep -qi "discharging" "$batpath/status" && echo "true" || echo "false")
#         bat_capacity="$batpath/capacity"
#         if [ -r "$bat_capacity" ]; then
#           charge=$(awk -v charge="$charge" -v capacity="$(cat "$bat_capacity")" 'BEGIN { print charge + capacity / 100 }')
#         else
#           bat_energy_full="$batpath/energy_full"
#           bat_energy_now="$batpath/energy_now"
#           if [ -r "$bat_energy_full" ] && [ -r "$bat_energy_now" ]; then
#             charge=$(awk -v charge="$charge" -v energy_now="$(cat "$bat_energy_now")" -v energy_full="$(cat "$bat_energy_full")" 'BEGIN { print charge + energy_now / energy_full }')
#           fi
#         fi
#         count=$((count + 1))
#       done  << EOF
# $(find /sys/class/power_supply -maxdepth 1 -iname '*bat*')
# EOF
#       ;;
#     *CYGWIN*|*MSYS*|*MINGW*)
#       while IFS= read -r line; do
#         [ -z "$line" ] && continue
#         discharging=$(printf '%s' "$line" | awk '{ s = ($1 == 1) ? "true" : "false"; print s }')
#         charge=$(printf '%s' "$line" | awk -v charge="$charge" '{ print charge + $2 / 100 }')
#         count=$((count + 1))
#       done  << EOF
# $(wmic path Win32_Battery get BatteryStatus, EstimatedChargeRemaining 2> /dev/null | tr -d '\r' | tail -n +2 || true)
# EOF
#       ;;
#     *OpenBSD*)
#       for batid in 0 1 2; do
#         sysctl -n "hw.sensors.acpibat$batid.raw0" 2>&1 | grep -q 'not found' && continue
#         discharging=$(sysctl -n "hw.sensors.acpibat$batid.raw0" | grep -q 1 && echo "true" || echo "false")
#         if sysctl -n "hw.sensors.acpibat$batid" | grep -q amphour; then
#           charge=$(awk -v charge="$charge" -v remaining="$(sysctl -n hw.sensors.acpibat$batid.amphour3 | cut -d' ' -f1)" -v full="$(sysctl -n hw.sensors.acpibat$batid.amphour0 | cut -d' ' -f1)" 'BEGIN { print charge + remaining / full }')
#         else
#           charge=$(awk -v charge="$charge" -v remaining="$(sysctl -n hw.sensors.acpibat$batid.watthour3 | cut -d' ' -f1)" -v full="$(sysctl -n hw.sensors.acpibat$batid.watthour0 | cut -d' ' -f1)" 'BEGIN { print charge + remaining / full }')
#         fi
#         count=$((count + 1))
#       done
#       ;;
#   esac
#   [ "$count" -ne 0 ] && charge=$(awk -v charge="$charge" -v count="$count" 'BEGIN { print charge / count }') || true
# }
#
# _battery_status() {
#   _battery_info
#   if [ "$charge" = 0 ]; then
#     tmux set -ug '@battery_status'
#     return
#   fi
#
#   battery_status_charging=$1
#   battery_status_discharging=$2
#   if [ x"$discharging" = x"true" ]; then
#     battery_status="$battery_status_discharging"
#   else
#     battery_status="$battery_status_charging"
#   fi
#
#   tmux set -g '@battery_status' "$battery_status"
# }
#
# _battery_bar() {
#   _battery_info
#   if [ "$charge" = 0 ]; then
#     tmux  set -ug '@battery_bar'     \;\
#           set -ug '@battery_hbar'    \;\
#           set -ug '@battery_vbar'    \;\
#           set -ug '@battery_percentage'
#     return
#   fi
#
#   battery_bar_symbol_full=$1
#   battery_bar_symbol_empty=$2
#   battery_bar_length=$3
#   battery_bar_palette=$4
#   battery_hbar_palette=$5
#   battery_vbar_palette=$6
#
#   if [ x"$battery_bar_length" = x"auto" ]; then
#     columns=$(tmux -q display -p '#{client_width}' 2> /dev/null || echo 80)
#     if [ "$columns" -ge 80 ]; then
#       battery_bar_length=10
#     else
#       battery_bar_length=5
#     fi
#   fi
#
#   if echo "$battery_bar_palette" | grep -q -E '^heat|gradient(,[#a-z0-9]{7,9})?$'; then
#     # shellcheck disable=SC2086
#     { set -f; IFS=,; set -- $battery_bar_palette; unset IFS; set +f; }
#     palette_style=$1
#     battery_bg=${2:-none}
#     [ x"$palette_style" = x"gradient" ] && \
#       palette="196 202 208 214 220 226 190 154 118 82 46"
#     [ x"$palette_style" = x"heat" ] && \
#       palette="243 245 247 144 143 142 184 214 208 202 196"
#
#     palette=$(echo "$palette" | awk -v n="$battery_bar_length" '{ for (i = 0; i < n; ++i) printf $(1 + (i * NF / n))" " }')
#     eval set -- "$palette"
#
#     full=$(awk "BEGIN { printf \"%.0f\", ($charge) * $battery_bar_length }")
#     battery_bar="#[bg=$battery_bg]"
#     # shellcheck disable=SC2046
#     [ "$full" -gt 0 ] && \
#       battery_bar="$battery_bar$(printf "#[fg=colour%s]$battery_bar_symbol_full" $(echo "$palette" | cut -d' ' -f1-"$full"))"
#     # shellcheck disable=SC2046
#     empty=$((battery_bar_length - full))
#     # shellcheck disable=SC2046
#     [ "$empty" -gt 0 ] && \
#       battery_bar="$battery_bar$(printf "#[fg=colour%s]$battery_bar_symbol_empty" $(echo "$palette" | cut -d' ' -f$((full + 1))-$((full + empty))))"
#       eval battery_bar="$battery_bar#[fg=colour\${$((full == 0 ? 1 : full))}]"
#   elif echo "$battery_bar_palette" | grep -q -E '^(([#a-z0-9]{7,9}|none),?){3}$'; then
#     # shellcheck disable=SC2086
#     { set -f; IFS=,; set -- $battery_bar_palette; unset IFS; set +f; }
#     battery_full_fg=$1
#     battery_empty_fg=$2
#     battery_bg=$3
#
#     full=$(awk "BEGIN { printf \"%.0f\", ($charge) * $battery_bar_length }")
#     [ x"$battery_bg" != x"none" ] && \
#       battery_bar="#[bg=$battery_bg]"
#     #shellcheck disable=SC2046
#     [ "$full" -gt 0 ] && \
#       battery_bar="$battery_bar#[fg=$battery_full_fg]$(printf "%0.s$battery_bar_symbol_full" $(seq 1 "$full"))"
#     empty=$((battery_bar_length - full))
#     #shellcheck disable=SC2046
#     [ "$empty" -gt 0 ] && \
#       battery_bar="$battery_bar#[fg=$battery_empty_fg]$(printf "%0.s$battery_bar_symbol_empty" $(seq 1 "$empty"))" && \
#       battery_bar="$battery_bar#[fg=$battery_empty_fg]"
#   fi
#
#   if echo "$battery_hbar_palette" | grep -q -E '^heat|gradient(,[#a-z0-9]{7,9})?$'; then
#     # shellcheck disable=SC2086
#     { set -f; IFS=,; set -- $battery_hbar_palette; unset IFS; set +f; }
#     palette_style=$1
#     [ x"$palette_style" = x"gradient" ] && \
#       palette="196 202 208 214 220 226 190 154 118 82 46"
#     [ x"$palette_style" = x"heat" ] && \
#       palette="233 234 235 237 239 241 243 245 247 144 143 142 184 214 208 202 196"
#
#     palette=$(echo "$palette" | awk -v n="$battery_bar_length" '{ for (i = 0; i < n; ++i) printf $(1 + (i * NF / n))" " }')
#     eval set -- "$palette"
#
#     full=$(awk "BEGIN { printf \"%.0f\", ($charge) * $battery_bar_length }")
#     eval battery_hbar_fg="colour\${$((full == 0 ? 1 : full))}"
#   elif echo "$battery_hbar_palette" | grep -q -E '^([#a-z0-9]{7,9},?){3}$'; then
#     # shellcheck disable=SC2086
#     { set -f; IFS=,; set -- $battery_hbar_palette; unset IFS; set +f; }
#
#     # shellcheck disable=SC2046
#     eval $(awk "BEGIN { printf \"battery_hbar_fg=$%d\", (($charge) - 0.001) * $# + 1 }")
#   fi
#
#   eval set -- "▏ ▎ ▍ ▌ ▋ ▊ ▉ █"
#   # shellcheck disable=SC2046
#   eval $(awk "BEGIN { printf \"battery_hbar_symbol=$%d\", ($charge) * ($# - 1) + 1 }")
#   battery_hbar="#[fg=${battery_hbar_fg?}]${battery_hbar_symbol?}"
#
#   if echo "$battery_vbar_palette" | grep -q -E '^heat|gradient(,[#a-z0-9]{7,9})?$'; then
#     # shellcheck disable=SC2086
#     { set -f; IFS=,; set -- $battery_vbar_palette; unset IFS; set +f; }
#     palette_style=$1
#     [ x"$palette_style" = x"gradient" ] && \
#       palette="196 202 208 214 220 226 190 154 118 82 46"
#     [ x"$palette_style" = x"heat" ] && \
#       palette="233 234 235 237 239 241 243 245 247 144 143 142 184 214 208 202 196"
#
#     palette=$(echo "$palette" | awk -v n="$battery_bar_length" '{ for (i = 0; i < n; ++i) printf $(1 + (i * NF / n))" " }')
#     eval set -- "$palette"
#
#     full=$(awk "BEGIN { printf \"%.0f\", ($charge) * $battery_bar_length }")
#     eval battery_vbar_fg="colour\${$((full == 0 ? 1 : full))}"
#   elif echo "$battery_vbar_palette" | grep -q -E '^([#a-z0-9]{7,9},?){3}$'; then
#     # shellcheck disable=SC2086
#     { set -f; IFS=,; set -- $battery_vbar_palette; unset IFS; set +f; }
#
#     # shellcheck disable=SC2046
#     eval $(awk "BEGIN { printf \"battery_vbar_fg=$%d\", (($charge) - 0.001) * $# + 1 }")
#   fi
#
#   eval set -- "▁ ▂ ▃ ▄ ▅ ▆ ▇ █"
#   # shellcheck disable=SC2046
#   eval $(awk "BEGIN { printf \"battery_vbar_symbol=$%d\", ($charge) * ($# - 1) + 1 }")
#   battery_vbar="#[fg=${battery_vbar_fg?}]${battery_vbar_symbol?}"
#
#   battery_percentage="$(awk "BEGIN { printf \"%.0f%%\", ($charge) * 100 }")"
#
#   tmux  set -g '@battery_status' "$battery_status" \;\
#         set -g '@battery_bar' "$battery_bar" \;\
#         set -g '@battery_hbar' "$battery_hbar" \;\
#         set -g '@battery_vbar' "$battery_vbar" \;\
#         set -g '@battery_percentage' "$battery_percentage"
# }
#
# _tty_info() {
#   tty="${1##/dev/}"
#   case "$_uname_s" in
#     *CYGWIN*)
#       ps -al | tail -n +2 | awk -v tty="$tty" '
#         ((/ssh/ && !/-W/) || !/ssh/) && $5 == tty {
#           user[$1] = $6; parent[$1] = $2; child[$2] = $1
#         }
#         END {
#           for (i in parent)
#           {
#             j = i
#             while (parent[j])
#               j = parent[j]
#
#             if (!(i in child) && j != 1)
#             {
#               file = "/proc/" i "/cmdline"; getline command < file; close(file)
#               gsub(/\0/, " ", command)
#               "id -un " user[i] | getline username
#               print i":"username":"command
#               exit
#             }
#           }
#         }
#       '
#       ;;
#     *)
#       ps -t "$tty" -o user=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX -o pid= -o ppid= -o command= | awk '
#         NR > 1 && ((/ssh/ && !/-W/) || !/ssh/) {
#           user[$2] = $1; parent[$2] = $3; child[$3] = $2; pid=$2; $1 = $2 = $3 = ""; command[pid] = substr($0,4)
#         }
#         END {
#           for (i in parent)
#           {
#             j = i
#             while (parent[j])
#               j = parent[j]
#
#             if (!(i in child) && j != 1)
#             {
#               print i":"user[i]":"command[i]
#               exit
#             }
#           }
#         }
#       '
#       ;;
#   esac
# }
#
# _ssh_or_mosh_args() {
#   case "$1" in
#     *ssh*)
#       args=$(printf '%s' "$1" | perl -n -e 'print if s/(.*?)\bssh\b\s+(.*)/\2/')
#       ;;
#     *mosh-client*)
#       args=$(printf '%s' "$1" | sed -E -e 's/.*mosh-client -# (.*)\|.*$/\1/' -e 's/-[^ ]*//g' -e 's/\d:\d//g')
#       ;;
#   esac
#
#  printf '%s' "$args"
# }
#
# _username() {
#   tty=${1:-$(tmux display -p '#{pane_tty}')}
#   ssh_only=$2
#
#   tty_info=$(_tty_info "$tty")
#   command=${tty_info#*:}
#   command=${command#*:}
#
#   ssh_or_mosh_args=$(_ssh_or_mosh_args "$command")
#   if [ -n "$ssh_or_mosh_args" ]; then
#     # shellcheck disable=SC2086
#     username=$(ssh -G $ssh_or_mosh_args 2>/dev/null | awk '/^user / { print $2; exit }')
#     # shellcheck disable=SC2086
#     [ -z "$username" ] && username=$(ssh -T -o ControlPath=none -o ProxyCommand="sh -c 'echo %%username%% %r >&2'" $ssh_or_mosh_args 2>&1 | awk '/^%username% / { print $2; exit }')
#   else
#     if ! _is_enabled "$ssh_only"; then
#       username=${tty_info#*:}
#       username=${username%%:*}
#     fi
#   fi
#
#   printf '%s\n' "$username"
# }
#
# _hostname() {
#   tty=${1:-$(tmux display -p '#{pane_tty}')}
#   ssh_only=$2
#
#   tty_info=$(_tty_info "$tty")
#   command=${tty_info#*:}
#   command=${command#*:}
#
#   ssh_or_mosh_args=$(_ssh_or_mosh_args "$command")
#   if [ -n "$ssh_or_mosh_args" ]; then
#     # shellcheck disable=SC2086
#     hostname=$(ssh -G $ssh_or_mosh_args 2>/dev/null | awk '/^hostname / { print $2; exit }')
#     # shellcheck disable=SC2086
#     [ -z "$hostname" ] && hostname=$(ssh -T -o ControlPath=none -o ProxyCommand="sh -c 'echo %%hostname%% %h >&2'" $ssh_or_mosh_args 2>&1 | awk '/^%hostname% / { print $2; exit }')
#
#     case "$hostname" in
#         *[a-z-].*)
#             hostname=${hostname%%.*}
#             ;;
#         127.0.0.1)
#             hostname="localhost"
#             ;;
#     esac
#   else
#     if ! _is_enabled "$ssh_only"; then
#       hostname=$3
#     fi
#   fi
#
#   printf '%s\n' "$hostname"
# }
#
# _root() {
#   tty=${1:-$(tmux display -p '#{pane_tty}')}
#   root=$2
#
#   username=$(_username "$tty" false)
#
#   [ x"$username" = x"root" ] && echo "$root"
# }
#
# _uptime() {
#   case "$_uname_s" in
#     *Darwin*|*FreeBSD*)
#       boot=$(sysctl -q -n kern.boottime | awk -F'[ ,:]+' '{ print $4 }')
#       now=$(date +%s)
#       ;;
#     *Linux*|*CYGWIN*|*MSYS*|*MINGW*)
#       boot=0
#       now=$(cut -d' ' -f1 < /proc/uptime)
#       ;;
#     *OpenBSD*)
#       boot=$(sysctl -n kern.boottime)
#       now=$(date +%s)
#   esac
#   # shellcheck disable=SC1004
#   awk -v boot="$boot" -v now="$now" '
#     BEGIN {
#       uptime = now - boot
#       y = int(uptime / 31536000)
#       dy = int(uptime / 86400) % 365
#       d = int(uptime / 86400)
#       h = int(uptime / 3600) % 24
#       m = int(uptime / 60) % 60
#       s = int(uptime) % 60
#
#       system("tmux  set -g @uptime_y " y + 0 " \\; " \
#                    "set -g @uptime_dy " dy + 0 " \\; " \
#                    "set -g @uptime_d " d + 0 " \\; " \
#                    "set -g @uptime_h " h + 0 " \\; " \
#                    "set -g @uptime_m " m + 0 " \\; " \
#                    "set -g @uptime_s " s + 0)
#     }'
# }
#
# _loadavg() {
#   case "$_uname_s" in
#     *Darwin*|*FreeBSD*)
#       tmux set -g @loadavg "$(sysctl -q -n vm.loadavg | cut -d' ' -f2)"
#       ;;
#     *Linux*|*CYGWIN*)
#       tmux set -g @loadavg "$(cut -d' ' -f1 < /proc/loadavg)"
#       ;;
#     *OpenBSD*)
#       tmux set -g @loadavg "$(sysctl -q -n vm.loadavg | cut -d' ' -f1)"
#       ;;
#   esac
# }
#
# _split_window_ssh() {
#   tty=${1:-$(tmux display -p '#{pane_tty}')}
#   shift
#
#   tty_info=$(_tty_info "$tty")
#   command=${tty_info#*:}
#   command=${command#*:}
#
#   case "$command" in
#     *mosh-client*)
#       # shellcheck disable=SC2046
#        tmux split-window "$@" mosh $(echo "$command" | sed -E -e 's/.*mosh-client -# (.*)\|.*$/\1/')
#      ;;
#     *ssh*)
#       # shellcheck disable=SC2046
#       tmux split-window "$@" $(echo "$command" | sed -e 's/;/\\;/g')
#       ;;
#     *)
#       tmux split-window "$@"
#   esac
# }
#
# _split_window() {
#   _split_window_ssh "$@"
# }
#
# _apply_overrides() {
#   tmux_conf_theme_24b_colour=${tmux_conf_theme_24b_colour:-false}
#   if _is_enabled "$tmux_conf_theme_24b_colour"; then
#   case "$TERM" in
#     screen-*|tmux-*)
#       ;;
#     *)
#       tmux set-option -ga terminal-overrides ",*256col*:Tc"
#       ;;
#   esac
#   fi
# }
#
# _apply_bindings() {
#   cfg=$(mktemp) && trap 'rm -f $cfg*' EXIT
#
#   tmux list-keys | grep -vF 'tmux.conf.local' | grep -E 'new-window|split(-|_)window|new-session|copy-selection|copy-pipe' > "$cfg"
#
#   # tmux 3.0 doesn't include 02254d1e5c881be95fd2fc37b4c4209640b6b266 and the
#   # output of list-keys can be truncated
#   perl -p -i -e "s/'#\{\?window_zoomed_flag,Unzoom,Zoom\}' 'z' \{resize-pane -$/'#{?window_zoomed_flag,Unzoom,Zoom}' 'z' {resize-pane -Z}\"/g" "$cfg"
#
#   perl -p -i -e "
#     s/\bnew-window\b([^;}\n]*?)(?:\s+-c\s+((?:\\\\\")?|\"?|'?)#\{pane_current_path\}\2)/new-window\1/g
#     ;
#     s/\brun-shell\b\s+(\"|')cut\s+-c3-\s+~\/\.tmux\.conf\s+\|\s+sh\s+-s\s+_split_window\s+#\{pane_tty\}([^\n\1]*)(\s+-c\s+((?:\\\\\")?|\"?|'?)#\{pane_current_path\}\4)([^\n\1]*)\1/run-shell \1cut -c3- ~\/.tmux.conf | sh -s _split_window #{pane_tty}\2\5\1/g
#     ;
#     s/\brun-shell\b(\s+((?:\\\\\")?|\"?|'?)cut\s+-c3-\s+~\/\.tmux\.conf\s+\|\s+sh\s+-s\s+_split_window\s+((?:\\\\\")?|\"?|'?)#\{pane_tty\}\3)(.*?)\2/split-window\4/g
#     ;
#     s/\bsplit-window\b([^;}\n]*?)(?:\s+-c\s+((?:\\\\\")?|\"?|'?)#\{pane_current_path\}\2)/split-window\1/g" \
#     "$cfg"
#
#   tmux_conf_new_window_retain_current_path=${tmux_conf_new_window_retain_current_path:-false}
#   if _is_enabled "$tmux_conf_new_window_retain_current_path"; then
#     perl -p -i -e "
#       s/\bnew-window\b(?!\s+-)/{$&}/g if /\bdisplay-menu\b/
#       ;
#       s/\bnew-window\b/new-window -c '#\{pane_current_path\}'/g" \
#       "$cfg"
#   fi
#
#   perl -p -i -e "
#     s/\bsplit-window\b((?:(?:[ \t]+-[bdfhIvP])|(?:[ \t]+-[celtF][ \t]+(?!\bssh\b)[^\s]+))*)?(?:\s+(\bssh\b))((?:(?:[ \t]+-[bdfhIvP])|(?:[ \t]+-[celtF][ \t]+(?!\bssh\b)[^\s]+))*)?/run-shell 'cut -c3- ~\/\.tmux\.conf | sh -s _split_window_ssh #\{pane_tty\}\1'/g if /\bsplit-window\b((?:(?:[ \t]+-[bdfhIvP])|(?:[ \t]+-[celtF][ \t]+(?!ssh)[^\s]+))*)?(?:\s+(ssh))((?:(?:[ \t]+-[bdfhIvP])|(?:[ \t]+-[celtF][ \t]+(?!ssh)[^\s]+))*)?/"\
#   "$cfg"
#
#   tmux_conf_new_pane_retain_current_path=${tmux_conf_new_pane_retain_current_path:-true}
#   tmux_conf_new_pane_reconnect_ssh=${tmux_conf_new_pane_reconnect_ssh:-false}
#   if _is_enabled "$tmux_conf_new_pane_reconnect_ssh"; then
#     perl -p -i -e "s/\bsplit-window\b([^;}\n\"]*)/run-shell 'cut -c3- ~\/\.tmux\.conf | sh -s _split_window #\{pane_tty\}\1'/g" "$cfg"
#   fi
#
#   if _is_enabled "$tmux_conf_new_pane_retain_current_path"; then
#     perl -p -i -e "
#       s/\bsplit-window\b(?!\s+-)/{$&}/g if /\bdisplay-menu\b/
#       ;
#       s/\bsplit-window\b/split-window -c '#{pane_current_path}'\1/g
#       ;
#       s/\brun-shell\b\s+'cut\s+-c3-\s+~\/\.tmux\.conf\s+\|\s+sh\s+-s\s+_split_window(_ssh)?\s+#\{pane_tty\}([^}\n']*)'/run-shell 'cut -c3- ~\/.tmux.conf | sh -s _split_window\1 #\{pane_tty\} -c \\\\\"#\{pane_current_path\}\\\\\"\2'/g if /\bdisplay-menu\b/
#       ;
#       s/\brun-shell\b\s+'cut\s+-c3-\s+~\/\.tmux\.conf\s+\|\s+sh\s+-s\s+_split_window(_ssh)?\s+#\{pane_tty\}([^}\n']*)'/run-shell 'cut -c3- ~\/.tmux.conf | sh -s _split_window\1 #\{pane_tty\} -c \"#\{pane_current_path\}\"\2'/g" \
#       "$cfg"
#   fi
#
#   tmux_conf_new_session_prompt=${tmux_conf_new_session_prompt:-false}
#   if _is_enabled "$tmux_conf_new_session_prompt"; then
#     perl -p -i \
#       -e "s/(?<!command-prompt -p )\b(new-session)\b(?!\s+-)/{$&}/g if /\bdisplay-menu\b/" \
#       -e ';' \
#       -e "s/(?<!\bcommand-prompt -p )\bnew-session\b(?! -s)/command-prompt -p new-session 'new-session -s \"%%\"'/g" \
#       "$cfg"
#   else
#     perl -p -i -e "s/\bcommand-prompt\s+-p\s+new-session\s+'new-session\s+-s\s+\"%%\"'/new-session/g" "$cfg"
#   fi
#
#   tmux_conf_copy_to_os_clipboard=${tmux_conf_copy_to_os_clipboard:-false}
#   command -v pbcopy > /dev/null 2>&1 && command='pbcopy'
#   command -v reattach-to-user-namespace > /dev/null 2>&1 && command='reattach-to-user-namespace pbcopy'
#   command -v xsel > /dev/null 2>&1 && command='xsel -i -b'
#   ! command -v xsel > /dev/null 2>&1 && command -v xclip > /dev/null 2>&1 && command='xclip -i -selection clipboard > \/dev\/null 2>\&1'
#   command -v clip.exe > /dev/null 2>&1 && command='clip\.exe'
#   [ -c /dev/clipboard ] && command='cat > \/dev\/clipboard'
#
#   if [ -n "$command" ]; then
#     if _is_enabled "$tmux_conf_copy_to_os_clipboard"; then
#       perl -p -i -e "s/\bcopy-selection(-and-cancel)?\b/copy-pipe\1 '$command'/g" "$cfg"
#     else
#       perl -p -i -e "s/\bcopy-pipe(-and-cancel)?\b\s+(\"|')?$command\2/copy-selection\1/g" "$cfg"
#     fi
#   fi
#
#   # until tmux >= 3.0, output of tmux list-keys can't be consumed back by tmux source-file without applying some escapings
#   awk < "$cfg" \
#     '{i = $2 == "-T" ? 4 : 5; gsub(/^[;]$/, "\\\\&", $i); gsub(/^[$"#~]$/, "'"'"'&'"'"'", $i); gsub(/^['"'"']$/, "\"&\"", $i); print}' > "$cfg.in"
#
#   # ignore bindings with errors
#   if ! tmux source-file "$cfg.in"; then
#     verbose_flag=$(tmux source-file -v /dev/null 2> /dev/null && printf -- '-v' || true)
#     while ! out=$(tmux source-file "$verbose_flag" "$cfg.in"); do
#       line=$(printf "%s" "$out" | tail -1 | cut -d':' -f2)
#       perl -n -i -e "if ($. != $line) { print }" "$cfg.in"
#     done
#   fi
# }
#
# _apply_theme() {
#
#   # -- panes -------------------------------------------------------------
#
#   tmux_conf_theme_window_fg=${tmux_conf_theme_window_fg:-default}
#   tmux_conf_theme_window_bg=${tmux_conf_theme_window_bg:-default}
#   tmux_conf_theme_highlight_focused_pane=${tmux_conf_theme_highlight_focused_pane:-false}
#   tmux_conf_theme_focused_pane_fg=${tmux_conf_theme_focused_pane_fg:-default} # default
#   tmux_conf_theme_focused_pane_bg=${tmux_conf_theme_focused_pane_bg:-#0087d7} # light blue
#
#   window_style="fg=$tmux_conf_theme_window_fg,bg=$tmux_conf_theme_window_bg"
#   if _is_enabled "$tmux_conf_theme_highlight_focused_pane"; then
#     window_active_style="fg=$tmux_conf_theme_focused_pane_fg,bg=$tmux_conf_theme_focused_pane_bg"
#   else
#     window_active_style="default"
#   fi
#
#   tmux_conf_theme_pane_border_style=${tmux_conf_theme_pane_border_style:-thin}
#   tmux_conf_theme_pane_border=${tmux_conf_theme_pane_border:-#444444}               # light gray
#   tmux_conf_theme_pane_active_border=${tmux_conf_theme_pane_active_border:-#00afff} # light blue
#   tmux_conf_theme_pane_border_fg=${tmux_conf_theme_pane_border_fg:-$tmux_conf_theme_pane_border}
#   tmux_conf_theme_pane_active_border_fg=${tmux_conf_theme_pane_active_border_fg:-$tmux_conf_theme_pane_active_border}
#   case "$tmux_conf_theme_pane_border_style" in
#     fat)
#       tmux_conf_theme_pane_border_bg=${tmux_conf_theme_pane_border_bg:-$tmux_conf_theme_pane_border_fg}
#       tmux_conf_theme_pane_active_border_bg=${tmux_conf_theme_pane_active_border_bg:-$tmux_conf_theme_pane_active_border_fg}
#       ;;
#     thin|*)
#       tmux_conf_theme_pane_border_bg=${tmux_conf_theme_pane_border_bg:-default}
#       tmux_conf_theme_pane_active_border_bg=${tmux_conf_theme_pane_active_border_bg:-default}
#       ;;
#   esac
#
#   tmux_conf_theme_pane_indicator=${tmux_conf_theme_pane_indicator:-#00afff}               # light blue
#   tmux_conf_theme_pane_active_indicator=${tmux_conf_theme_pane_active_indicator:-#00afff} # light blue
#
#   # -- status line -------------------------------------------------------
#
#   tmux_conf_theme_left_separator_main=$(_decode_unicode_escapes "${tmux_conf_theme_left_separator_main-}")
#   tmux_conf_theme_left_separator_sub=$(_decode_unicode_escapes "${tmux_conf_theme_left_separator_sub-|}")
#   tmux_conf_theme_right_separator_main=$(_decode_unicode_escapes "${tmux_conf_theme_right_separator_main-}")
#   tmux_conf_theme_right_separator_sub=$(_decode_unicode_escapes "${tmux_conf_theme_right_separator_sub-|}")
#
#   tmux_conf_theme_message_fg=${tmux_conf_theme_message_fg:-#000000}   # black
#   tmux_conf_theme_message_bg=${tmux_conf_theme_message_bg:-#ffff00}   # yellow
#   tmux_conf_theme_message_attr=${tmux_conf_theme_message_attr:-bold}
#
#   tmux_conf_theme_message_command_fg=${tmux_conf_theme_message_command_fg:-#ffff00} # yellow
#   tmux_conf_theme_message_command_bg=${tmux_conf_theme_message_command_bg:-#000000} # black
#   tmux_conf_theme_message_command_attr=${tmux_conf_theme_message_command_attr:-bold}
#
#   tmux_conf_theme_mode_fg=${tmux_conf_theme_mode_fg:-#000000} # black
#   tmux_conf_theme_mode_bg=${tmux_conf_theme_mode_bg:-#ffff00} # yellow
#   tmux_conf_theme_mode_attr=${tmux_conf_theme_mode_attr:-bold}
#
#   tmux_conf_theme_status_fg=${tmux_conf_theme_status_fg:-#8a8a8a} # white
#   tmux_conf_theme_status_bg=${tmux_conf_theme_status_bg:-#080808} # dark gray
#   tmux_conf_theme_status_attr=${tmux_conf_theme_status_attr:-none}
#
#   tmux_conf_theme_terminal_title=${tmux_conf_theme_terminal_title:-#h ❐ #S ● #I #W}
#
#   tmux_conf_theme_terminal_title=$(echo "$tmux_conf_theme_terminal_title" | sed \
#     -e 's%#{circled_window_index}%#(cut -c3- ~/.tmux.conf | sh -s _circled #I)%g' \
#     -e 's%#{circled_session_name}%#(cut -c3- ~/.tmux.conf | sh -s _circled #S)%g' \
#     -e 's%#{username}%#(cut -c3- ~/.tmux.conf | sh -s _username #{pane_tty} false #D)%g' \
#     -e 's%#{hostname}%#(cut -c3- ~/.tmux.conf | sh -s _hostname #{pane_tty} false #h #D)%g' \
#     -e 's%#{username_ssh}%#(cut -c3- ~/.tmux.conf | sh -s _username #{pane_tty} true #D)%g' \
#     -e 's%#{hostname_ssh}%#(cut -c3- ~/.tmux.conf | sh -s _hostname #{pane_tty} true #h #D)%g')
#
#   tmux_conf_theme_window_status_fg=${tmux_conf_theme_window_status_fg:-#8a8a8a} # white
#   tmux_conf_theme_window_status_bg=${tmux_conf_theme_window_status_bg:-#080808} # dark gray
#   tmux_conf_theme_window_status_attr=${tmux_conf_theme_window_status_attr:-none}
#   tmux_conf_theme_window_status_format=${tmux_conf_theme_window_status_format:-#I #W}
#
#   tmux_conf_theme_window_status_current_fg=${tmux_conf_theme_window_status_current_fg:-#000000} # black
#   tmux_conf_theme_window_status_current_bg=${tmux_conf_theme_window_status_current_bg:-#00afff} # light blue
#   tmux_conf_theme_window_status_current_attr=${tmux_conf_theme_window_status_current_attr:-bold}
#   tmux_conf_theme_window_status_current_format=${tmux_conf_theme_window_status_current_format:-#I #W}
#   if [ x"$(tmux show -g -v status-justify)" = x"right" ]; then
#     tmux_conf_theme_window_status_current_format="#[fg=$tmux_conf_theme_window_status_current_bg,bg=$tmux_conf_theme_status_bg,none]$tmux_conf_theme_right_separator_main#[fg=$tmux_conf_theme_window_status_current_fg,bg=$tmux_conf_theme_window_status_current_bg,$tmux_conf_theme_window_status_current_attr] $tmux_conf_theme_window_status_current_format #[fg=$tmux_conf_theme_window_status_current_bg,bg=$tmux_conf_theme_status_bg,none,reverse]$tmux_conf_theme_right_separator_main"
#   else
#     tmux_conf_theme_window_status_current_format="#[fg=$tmux_conf_theme_window_status_current_bg,bg=$tmux_conf_theme_status_bg,none,reverse]$tmux_conf_theme_left_separator_main#[noreverse]#[fg=$tmux_conf_theme_window_status_current_fg,bg=$tmux_conf_theme_window_status_current_bg,$tmux_conf_theme_window_status_current_attr] $tmux_conf_theme_window_status_current_format #[fg=$tmux_conf_theme_window_status_current_bg,bg=$tmux_conf_theme_status_bg]$tmux_conf_theme_left_separator_main"
#   fi
#
#   tmux_conf_theme_window_status_format=$(echo "$tmux_conf_theme_window_status_format" | sed \
#     -e 's%#{circled_window_index}%#(cut -c3- ~/.tmux.conf | sh -s _circled #I)%g' \
#     -e 's%#{circled_session_name}%#(cut -c3- ~/.tmux.conf | sh -s _circled #S)%g' \
#     -e 's%#{username}%#(cut -c3- ~/.tmux.conf | sh -s _username #{pane_tty} false #D)%g' \
#     -e 's%#{hostname}%#(cut -c3- ~/.tmux.conf | sh -s _hostname #{pane_tty} false #h #D)%g' \
#     -e 's%#{username_ssh}%#(cut -c3- ~/.tmux.conf | sh -s _username #{pane_tty} true #D)%g' \
#     -e 's%#{hostname_ssh}%#(cut -c3- ~/.tmux.conf | sh -s _hostname #{pane_tty} true #h #D)%g')
#   tmux_conf_theme_window_status_current_format=$(echo "$tmux_conf_theme_window_status_current_format" | sed \
#     -e 's%#{circled_window_index}%#(cut -c3- ~/.tmux.conf | sh -s _circled #I)%g' \
#     -e 's%#{circled_session_name}%#(cut -c3- ~/.tmux.conf | sh -s _circled #S)%g' \
#     -e 's%#{username}%#(cut -c3- ~/.tmux.conf | sh -s _username #{pane_tty} false #D)%g' \
#     -e 's%#{hostname}%#(cut -c3- ~/.tmux.conf | sh -s _hostname #{pane_tty} false #h #D)%g' \
#     -e 's%#{username_ssh}%#(cut -c3- ~/.tmux.conf | sh -s _username #{pane_tty} true #D)%g' \
#     -e 's%#{hostname_ssh}%#(cut -c3- ~/.tmux.conf | sh -s _hostname #{pane_tty} true #h #D)%g')
#
#   tmux_conf_theme_window_status_activity_fg=${tmux_conf_theme_window_status_activity_fg:-default}
#   tmux_conf_theme_window_status_activity_bg=${tmux_conf_theme_window_status_activity_bg:-default}
#   tmux_conf_theme_window_status_activity_attr=${tmux_conf_theme_window_status_activity_attr:-underscore}
#
#   tmux_conf_theme_window_status_bell_fg=${tmux_conf_theme_window_status_bell_fg:-#ffff00} # yellow
#   tmux_conf_theme_window_status_bell_bg=${tmux_conf_theme_window_status_bell_bg:-default}
#   tmux_conf_theme_window_status_bell_attr=${tmux_conf_theme_window_status_bell_attr:-blink,bold}
#
#   tmux_conf_theme_window_status_last_fg=${tmux_conf_theme_window_status_last_fg:-#00afff} # light blue
#   tmux_conf_theme_window_status_last_bg=${tmux_conf_theme_window_status_last_bg:-default}
#   tmux_conf_theme_window_status_last_attr=${tmux_conf_theme_window_status_last_attr:-none}
#
#   # -- indicators
#
#   tmux_conf_theme_pairing=${tmux_conf_theme_pairing:-👓 }           # U+1F453
#   tmux_conf_theme_pairing_fg=${tmux_conf_theme_pairing_fg:-#e4e4e4} # white
#   tmux_conf_theme_pairing_bg=${tmux_conf_theme_pairing_bg:-none}
#   tmux_conf_theme_pairing_attr=${tmux_conf_theme_pairing_attr:-none}
#
#   tmux_conf_theme_prefix=${tmux_conf_theme_prefix:-⌨ }            # U+2328
#   tmux_conf_theme_prefix_fg=${tmux_conf_theme_prefix_fg:-#e4e4e4} # white
#   tmux_conf_theme_prefix_bg=${tmux_conf_theme_prefix_bg:-none}
#   tmux_conf_theme_prefix_attr=${tmux_conf_theme_prefix_attr:-none}
#
#   tmux_conf_theme_root=${tmux_conf_theme_root:-!}
#   tmux_conf_theme_root_fg=${tmux_conf_theme_root_fg:-none}
#   tmux_conf_theme_root_bg=${tmux_conf_theme_root_bg:-none}
#   tmux_conf_theme_root_attr=${tmux_conf_theme_root_attr:-bold,blink}
#
#   tmux_conf_theme_synchronized=${tmux_conf_theme_synchronized:-🔒}  # U+1F512
#   tmux_conf_theme_synchronized_fg=${tmux_conf_theme_synchronized_fg:-none}
#   tmux_conf_theme_synchronized_bg=${tmux_conf_theme_synchronized_bg:-none}
#   tmux_conf_theme_synchronized_attr=${tmux_conf_theme_synchronized_attr:-none}
#
#   # -- status-left style
#
#   tmux_conf_theme_status_left=${tmux_conf_theme_status_left-' ❐ #S | ↑#{?uptime_y, #{uptime_y}y,}#{?uptime_d, #{uptime_d}d,}#{?uptime_h, #{uptime_h}h,}#{?uptime_m, #{uptime_m}m,} '}
#   tmux_conf_theme_status_left_fg=${tmux_conf_theme_status_left_fg:-#000000,#e4e4e4,#e4e4e4}  # black, white , white
#   tmux_conf_theme_status_left_bg=${tmux_conf_theme_status_left_bg:-#ffff00,#ff00af,#00afff}  # yellow, pink, white blue
#   tmux_conf_theme_status_left_attr=${tmux_conf_theme_status_left_attr:-bold,none,none}
#
#   if [ -n "$tmux_conf_theme_status_left" ]; then
#     status_left=$(echo "$tmux_conf_theme_status_left" | sed \
#       -e "s/#{pairing}/#[fg=$tmux_conf_theme_pairing_fg]#[bg=$tmux_conf_theme_pairing_bg]#[$tmux_conf_theme_pairing_attr]#{?session_many_attached,$tmux_conf_theme_pairing,}/g" \
#       -e "s/#{prefix}/#[fg=$tmux_conf_theme_prefix_fg]#[bg=$tmux_conf_theme_prefix_bg]#[$tmux_conf_theme_prefix_attr]#{?client_prefix,$tmux_conf_theme_prefix,}/g" \
#       -e "s%#{synchronized}%#[fg=$tmux_conf_theme_synchronized_fg]#[bg=$tmux_conf_theme_synchronized_bg]#[$tmux_conf_theme_synchronized_attr]#{?pane_synchronized,$tmux_conf_theme_synchronized,}%g" \
#       -e 's%#{circled_session_name}%#(cut -c3- ~/.tmux.conf | sh -s _circled #S)%g')
#
#     if [ -n "$(tmux display -p '#{version}')" ]; then
#       status_left=$(echo "$status_left" | sed \
#         -e "s%#{root}%#[fg=$tmux_conf_theme_root_fg]#[bg=$tmux_conf_theme_root_bg]#[$tmux_conf_theme_root_attr]#{?#{==:#(cut -c3- ~/.tmux.conf | sh -s _username #{pane_tty} #D),root},$tmux_conf_theme_root,}#[inherit]%g")
#     else
#       status_left=$(echo "$status_left" | sed \
#         -e "s%#{root}%#[fg=$tmux_conf_theme_root_fg]#[bg=$tmux_conf_theme_root_bg]#[$tmux_conf_theme_root_attr]#(cut -c3- ~/.tmux.conf | sh -s _root #{pane_tty} $tmux_conf_theme_root #D)#[inherit]%g")
#     fi
#
#     status_left=$(printf '%s' "$status_left" | awk \
#                       -v status_bg="$tmux_conf_theme_status_bg" \
#                       -v fg_="$tmux_conf_theme_status_left_fg" \
#                       -v bg_="$tmux_conf_theme_status_left_bg" \
#                       -v attr_="$tmux_conf_theme_status_left_attr" \
#                       -v mainsep="$tmux_conf_theme_left_separator_main" \
#                       -v subsep="$tmux_conf_theme_left_separator_sub" '
#       function subsplit(s, l, i, a, r)
#       {
#         l = split(s, a, ",")
#         for (i = 1; i <= l; ++i)
#         {
#           o = split(a[i], _, "(") - 1
#           c = split(a[i], _, ")") - 1
#           open += o - c
#           o_ = split(a[i], _, "{") - 1
#           c_ = split(a[i], _, "}") - 1
#           open_ += o_ - c_
#           o__ = split(a[i], _, "[") - 1
#           c__ = split(a[i], _, "]") - 1
#           open__ += o__ - c__
#
#           if (i == l)
#             r = sprintf("%s%s", r, a[i])
#           else if (open || open_ || open__)
#             r = sprintf("%s%s,", r, a[i])
#           else
#             r = sprintf("%s%s#[fg=%s,bg=%s,%s]%s", r, a[i], fg[j], bg[j], attr[j], subsep)
#         }
#
#         gsub(/#\[inherit\]/, sprintf("#[default]#[fg=%s,bg=%s,%s]", fg[j], bg[j], attr[j]), r)
#         return r
#       }
#       BEGIN {
#         FS = "|"
#         l1 = split(fg_, fg, ",")
#         l2 = split(bg_, bg, ",")
#         l3 = split(attr_, attr, ",")
#         l = l1 < l2 ? (l1 < l3 ? l1 : l3) : (l2 < l3 ? l2 : l3)
#       }
#       {
#         for (i = j = 1; i <= NF; ++i)
#         {
#           if (open || open_ || open__)
#             printf "|%s", subsplit($i)
#           else
#           {
#             if (i > 1)
#               printf "#[fg=%s,bg=%s,none]%s#[fg=%s,bg=%s,%s]%s", bg[j_], bg[j], mainsep, fg[j], bg[j], attr[j], subsplit($i)
#             else
#               printf "#[fg=%s,bg=%s,%s]%s", fg[j], bg[j], attr[j], subsplit($i)
#           }
#
#           if (!open && !open_ && !open__)
#           {
#             j_ = j
#             j = j % l + 1
#           }
#         }
#         printf "#[fg=%s,bg=%s,none]%s", bg[j_], status_bg, mainsep
#       }')
#   fi
#
#   status_left="$status_left "
#
#   # -- status-right style
#
#   tmux_conf_theme_status_right=${tmux_conf_theme_status_right-'#{pairing}#{prefix} #{battery_status} #{battery_bar} #{battery_percentage} , %R , %d %b | #{username} | #{hostname} '}
#   tmux_conf_theme_status_right=${tmux_conf_theme_status_right-'#{prefix}#{pairing}#{synchronized} #{?battery_status, #{battery_status},}#{?battery_bar, #{battery_bar},}#{?battery_percentage, #{battery_percentage},} , %R , %d %b | #{username}#{root} | #{hostname} '}
#   tmux_conf_theme_status_right_fg=${tmux_conf_theme_status_right_fg:-#8a8a8a,#e4e4e4,#000000} # light gray, white, black
#   tmux_conf_theme_status_right_bg=${tmux_conf_theme_status_right_bg:-#080808,#d70000,#e4e4e4} # dark gray, red, white
#   tmux_conf_theme_status_right_attr=${tmux_conf_theme_status_right_attr:-none,none,bold}
#
#   if [ -n "$tmux_conf_theme_status_right" ]; then
#     status_right=$(echo "$tmux_conf_theme_status_right" | sed \
#       -e "s/#{pairing}/#[fg=$tmux_conf_theme_pairing_fg]#[bg=$tmux_conf_theme_pairing_bg]#[$tmux_conf_theme_pairing_attr]#{?session_many_attached,$tmux_conf_theme_pairing,}/g" \
#       -e "s/#{prefix}/#[fg=$tmux_conf_theme_prefix_fg]#[bg=$tmux_conf_theme_prefix_bg]#[$tmux_conf_theme_prefix_attr]#{?client_prefix,$tmux_conf_theme_prefix,}/g" \
#       -e "s%#{synchronized}%#[fg=$tmux_conf_theme_synchronized_fg]#[bg=$tmux_conf_theme_synchronized_bg]#[$tmux_conf_theme_synchronized_attr]#{?pane_synchronized,$tmux_conf_theme_synchronized,}%g" \
#       -e 's%#{circled_session_name}%#(cut -c3- ~/.tmux.conf | sh -s _circled #S)%g')
#
#     if [ -n "$(tmux display -p '#{version}')" ]; then
#       status_right=$(echo "$status_right" | sed \
#         -e "s%#{root}%#[fg=$tmux_conf_theme_root_fg]#[bg=$tmux_conf_theme_root_bg]#[$tmux_conf_theme_root_attr]#{?#{==:#(cut -c3- ~/.tmux.conf | sh -s _username #{pane_tty} #D),root},$tmux_conf_theme_root,}#[inherit]%g")
#     else
#       status_right=$(echo "$status_right" | sed \
#         -e "s%#{root}%#[fg=$tmux_conf_theme_root_fg]#[bg=$tmux_conf_theme_root_bg]#[$tmux_conf_theme_root_attr]#(cut -c3- ~/.tmux.conf | sh -s _root #{pane_tty} $tmux_conf_theme_root #D)#[inherit]%g")
#     fi
#
#     status_right=$(printf '%s' "$status_right" | awk \
#                       -v status_bg="$tmux_conf_theme_status_bg" \
#                       -v fg_="$tmux_conf_theme_status_right_fg" \
#                       -v bg_="$tmux_conf_theme_status_right_bg" \
#                       -v attr_="$tmux_conf_theme_status_right_attr" \
#                       -v mainsep="$tmux_conf_theme_right_separator_main" \
#                       -v subsep="$tmux_conf_theme_right_separator_sub" '
#       function subsplit(s, l, i, a, r)
#       {
#         l = split(s, a, ",")
#         for (i = 1; i <= l; ++i)
#         {
#           o = split(a[i], _, "(") - 1
#           c = split(a[i], _, ")") - 1
#           open += o - c
#           o_ = split(a[i], _, "{") - 1
#           c_ = split(a[i], _, "}") - 1
#           open_ += o_ - c_
#           o__ = split(a[i], _, "[") - 1
#           c__ = split(a[i], _, "]") - 1
#           open__ += o__ - c__
#
#           if (i == l)
#             r = sprintf("%s%s", r, a[i])
#           else if (open || open_ || open__)
#             r = sprintf("%s%s,", r, a[i])
#           else
#             r = sprintf("%s%s#[fg=%s,bg=%s,%s]%s", r, a[i], fg[j], bg[j], attr[j], subsep)
#         }
#
#         gsub(/#\[inherit\]/, sprintf("#[default]#[fg=%s,bg=%s,%s]", fg[j], bg[j], attr[j]), r)
#         return r
#       }
#       BEGIN {
#         FS = "|"
#         l1 = split(fg_, fg, ",")
#         l2 = split(bg_, bg, ",")
#         l3 = split(attr_, attr, ",")
#         l = l1 < l2 ? (l1 < l3 ? l1 : l3) : (l2 < l3 ? l2 : l3)
#       }
#       {
#         for (i = j = 1; i <= NF; ++i)
#         {
#           if (open_ || open || open__)
#             printf "|%s", subsplit($i)
#           else
#             printf "#[fg=%s,bg=%s,none]%s#[fg=%s,bg=%s,%s]%s", bg[j], (i == 1) ? status_bg : bg[j_], mainsep, fg[j], bg[j], attr[j], subsplit($i)
#
#           if (!open && !open_ && !open__)
#           {
#             j_ = j
#             j = j % l + 1
#           }
#         }
#       }')
#   fi
#
#   # -- variables
#
#   tmux_conf_battery_bar_symbol_full=$(_decode_unicode_escapes "${tmux_conf_battery_bar_symbol_full:-◼}")
#   tmux_conf_battery_bar_symbol_empty=$(_decode_unicode_escapes "${tmux_conf_battery_bar_symbol_empty:-◻}")
#   tmux_conf_battery_bar_length=${tmux_conf_battery_bar_length:-auto}
#   tmux_conf_battery_bar_palette=${tmux_conf_battery_bar_palette:-gradient}
#   tmux_conf_battery_hbar_palette=${tmux_conf_battery_hbar_palette:-gradient}                                    # red, orange, green
#   tmux_conf_battery_vbar_palette=${tmux_conf_battery_vbar_palette:-gradient}                                    # red, orange, green
#   tmux_conf_battery_status_charging=$(_decode_unicode_escapes "${tmux_conf_battery_status_charging:-↑}")        # U+2191
#   tmux_conf_battery_status_discharging=$(_decode_unicode_escapes "${tmux_conf_battery_status_discharging:-↓}")  # U+2193
#
#   _pkillf 'cut -c3- ~/\.tmux\.conf \| sh -s _battery_bar'
#   _battery_info
#   if [ "$charge" != 0 ]; then
#     case "$status_left $status_right" in
#       *'#{battery_status}'*|*'#{battery_bar}'*|*'#{battery_hbar}'*|*'#{battery_vbar}'*|*'#{battery_percentage}'*)
#         status_left=$(echo "$status_left" | sed -E \
#           -e 's/#\{(\?)?battery_bar/#\{\1@battery_bar/g' \
#           -e 's/#\{(\?)?battery_hbar/#\{\1@battery_hbar/g' \
#           -e 's/#\{(\?)?battery_vbar/#\{\1@battery_vbar/g' \
#           -e 's/#\{(\?)?battery_status/#\{\1@battery_status/g' \
#           -e 's/#\{(\?)?battery_percentage/#\{\1@battery_percentage/g')
#         status_right=$(echo "$status_right" | sed -E \
#           -e 's/#\{(\?)?battery_bar/#\{\1@battery_bar/g' \
#           -e 's/#\{(\?)?battery_hbar/#\{\1@battery_hbar/g' \
#           -e 's/#\{(\?)?battery_vbar/#\{\1@battery_vbar/g' \
#           -e 's/#\{(\?)?battery_status/#\{\1@battery_status/g' \
#           -e 's/#\{(\?)?battery_percentage/#\{\1@battery_percentage/g')
#         interval=60
#         tmux run -b "trap 'exit 0' TERM; while :; do nice cut -c3- ~/.tmux.conf | sh -s _battery_bar \"$tmux_conf_battery_bar_symbol_full\" \"$tmux_conf_battery_bar_symbol_empty\" \"$tmux_conf_battery_bar_length\" \"$tmux_conf_battery_bar_palette\" \"$tmux_conf_battery_hbar_palette\" \"$tmux_conf_battery_vbar_palette\"; sleep $interval; done"
#         status_right="#(printf '\n'; nice cut -c3- ~/.tmux.conf | sh -s _battery_status \"$tmux_conf_battery_status_charging\" \"$tmux_conf_battery_status_discharging\")$status_right"
#         ;;
#     esac
#   fi
#
#   case "$status_left $status_right" in
#     *'#{username}'*|*'#{hostname}'*|*'#{username_ssh}'*|*'#{hostname_ssh}'*)
#       status_left=$(echo "$status_left" | sed \
#         -e 's%#{username}%#(cut -c3- ~/.tmux.conf | sh -s _username #{pane_tty} false #D)%g' \
#         -e 's%#{hostname}%#(cut -c3- ~/.tmux.conf | sh -s _hostname #{pane_tty} false #h #D)%g' \
#         -e 's%#{username_ssh}%#(cut -c3- ~/.tmux.conf | sh -s _username #{pane_tty} true #D)%g' \
#         -e 's%#{hostname_ssh}%#(cut -c3- ~/.tmux.conf | sh -s _hostname #{pane_tty} true #h #D)%g')
#       status_right=$(echo "$status_right" | sed \
#         -e 's%#{username}%#(cut -c3- ~/.tmux.conf | sh -s _username #{pane_tty} false #D)%g' \
#         -e 's%#{hostname}%#(cut -c3- ~/.tmux.conf | sh -s _hostname #{pane_tty} false #h #D)%g' \
#         -e 's%#{username_ssh}%#(cut -c3- ~/.tmux.conf | sh -s _username #{pane_tty} true #D)%g' \
#         -e 's%#{hostname_ssh}%#(cut -c3- ~/.tmux.conf | sh -s _hostname #{pane_tty} true #h #D)%g')
#       ;;
#   esac
#
#   _pkillf 'cut -c3- ~/\.tmux\.conf \| sh -s _uptime'
#   case "$status_left $status_right" in
#     *'#{uptime_d}'*|*'#{uptime_h}'*|*'#{uptime_m}'*|*'#{uptime_s}'*)
#       status_left=$(echo "$status_left" | sed -E \
#         -e 's/#\{(\?)?uptime_y/#\{\1@uptime_y/g' \
#         -e 's/#\{(\?)?uptime_d/#\{\1@uptime_d/g' \
#         -e '/@uptime_y/ s/@uptime_d/@uptime_dy/g' \
#         -e 's/#\{(\?)?uptime_h/#\{\1@uptime_h/g' \
#         -e 's/#\{(\?)?uptime_m/#\{\1@uptime_m/g' \
#         -e 's/#\{(\?)?uptime_s/#\{\1@uptime_s/g')
#       status_right=$(echo "$status_right" | sed -E \
#         -e 's/#\{(\?)?uptime_y/#\{\1@uptime_y/g' \
#         -e 's/#\{(\?)?uptime_d/#\{\1@uptime_d/g' \
#         -e '/@uptime_y/ s/@uptime_d/@uptime_dy/g' \
#         -e 's/#\{(\?)?uptime_h/#\{\1@uptime_h/g' \
#         -e 's/#\{(\?)?uptime_m/#\{\1@uptime_m/g' \
#         -e 's/#\{(\?)?uptime_s/#\{\1@uptime_s/g')
#       interval=60
#       case "$status_left $status_right" in
#         *'#{@uptime_s}'*)
#           interval=$(tmux show -gv status-interval)
#           ;;
#       esac
#       tmux run -b "trap 'exit 0' TERM; while :; do nice cut -c3- ~/.tmux.conf | sh -s _uptime; sleep $interval; done"
#       ;;
#   esac
#
#   _pkillf 'cut -c3- ~/\.tmux\.conf \| sh -s _loadavg'
#   case "$status_left $status_right" in
#     *'#{loadavg}'*)
#       status_left=$(echo "$status_left" | sed -E \
#         -e 's/#\{(\?)?loadavg/#\{\1@loadavg/g')
#       status_right=$(echo "$status_right" | sed -E \
#         -e 's/#\{(\?)?loadavg/#\{\1@loadavg/g')
#       interval=$(tmux show -gv status-interval)
#       tmux run -b "trap 'exit 0' TERM; while :; do nice cut -c3- ~/.tmux.conf | sh -s _loadavg; sleep $interval; done"
#       ;;
#   esac
#
#   # -- clock -------------------------------------------------------------
#
#   tmux_conf_theme_clock_colour=${tmux_conf_theme_clock_colour:-#00afff} # light blue
#   tmux_conf_theme_clock_style=${tmux_conf_theme_clock_style:-24}
#
#   tmux setw -g window-style "$window_style" \; setw -g window-active-style "$window_active_style" \;\
#        setw -g pane-border-style "fg=$tmux_conf_theme_pane_border_fg,bg=$tmux_conf_theme_pane_border_bg" \; set -g pane-active-border-style "fg=$tmux_conf_theme_pane_active_border_fg,bg=$tmux_conf_theme_pane_active_border_bg" \;\
#        set -g display-panes-colour "$tmux_conf_theme_pane_indicator" \; set -g display-panes-active-colour "$tmux_conf_theme_pane_active_indicator" \;\
#        set -g message-style "fg=$tmux_conf_theme_message_fg,bg=$tmux_conf_theme_message_bg,$tmux_conf_theme_message_attr" \;\
#        set -g message-command-style "fg=$tmux_conf_theme_message_command_fg,bg=$tmux_conf_theme_message_command_bg,$tmux_conf_theme_message_command_attr" \;\
#        setw -g mode-style "fg=$tmux_conf_theme_mode_fg,bg=$tmux_conf_theme_mode_bg,$tmux_conf_theme_mode_attr" \;\
#        set -g status-style "fg=$tmux_conf_theme_status_fg,bg=$tmux_conf_theme_status_bg,$tmux_conf_theme_status_attr"        \;\
#        set -g status-left-style "fg=$tmux_conf_theme_status_fg,bg=$tmux_conf_theme_status_bg,$tmux_conf_theme_status_attr"   \;\
#        set -g status-right-style "fg=$tmux_conf_theme_status_fg,bg=$tmux_conf_theme_status_bg,$tmux_conf_theme_status_attr" \;\
#        set -g set-titles-string "$(_decode_unicode_escapes "$tmux_conf_theme_terminal_title")" \;\
#        setw -g window-status-style "fg=$tmux_conf_theme_window_status_fg,bg=$tmux_conf_theme_window_status_bg,$tmux_conf_theme_window_status_attr" \;\
#        setw -g window-status-format "$(_decode_unicode_escapes "$tmux_conf_theme_window_status_format")" \;\
#        setw -g window-status-current-style "fg=$tmux_conf_theme_window_status_current_fg,bg=$tmux_conf_theme_window_status_current_bg,$tmux_conf_theme_window_status_current_attr" \;\
#        setw -g window-status-current-format "$(_decode_unicode_escapes "$tmux_conf_theme_window_status_current_format")" \;\
#        setw -g window-status-activity-style "fg=$tmux_conf_theme_window_status_activity_fg,bg=$tmux_conf_theme_window_status_activity_bg,$tmux_conf_theme_window_status_activity_attr" \;\
#        setw -g window-status-bell-style "fg=$tmux_conf_theme_window_status_bell_fg,bg=$tmux_conf_theme_window_status_bell_bg,$tmux_conf_theme_window_status_bell_attr" \;\
#        setw -g window-status-last-style "fg=$tmux_conf_theme_window_status_last_fg,bg=$tmux_conf_theme_window_status_last_bg,$tmux_conf_theme_window_status_last_attr" \;\
#        set -g status-left-length 1000 \; set -g status-left "$(_decode_unicode_escapes "$status_left")" \;\
#        set -g status-right-length 1000 \; set -g status-right "$(_decode_unicode_escapes "$status_right")" \;\
#        setw -g clock-mode-colour "$tmux_conf_theme_clock_colour" \;\
#        setw -g clock-mode-style "$tmux_conf_theme_clock_style"
# }
#
# _apply_configuration() {
#
#   if ! command -v perl > /dev/null 2>&1; then
#     tmux run -b 'tmux set display-time 3000 \; display "This configuration requires perl" \; set -u display-time'
#     return
#   fi
#   if ! command -v sed > /dev/null 2>&1; then
#     tmux run -b 'tmux set display-time 3000 \; display "This configuration requires sed" \; set -u display-time'
#     return
#   fi
#   if ! command -v awk > /dev/null 2>&1; then
#     tmux run -b 'tmux set display-time 3000 \; display "This configuration requires awk" \; set -u display-time'
#     return
#   fi
#
#   # see https://github.com/ChrisJohnsen/tmux-MacOSX-pasteboard
#   if command -v reattach-to-user-namespace > /dev/null 2>&1; then
#     default_shell="$(tmux show -gv default-shell)"
#     case "$default_shell" in
#       *fish)
#         tmux set -g default-command "reattach-to-user-namespace -l $default_shell"
#         ;;
#       *sh)
#         tmux set -g default-command "exec $default_shell... 2> /dev/null & reattach-to-user-namespace -l $default_shell"
#         ;;
#     esac
#   fi
#
#   case "$_uname_s" in
#     *CYGWIN*|*MSYS*)
#       # prevent Cygwin and MSYS2 from cd-ing into home directory when evaluating /etc/profile
#       tmux setenv -g CHERE_INVOKING 1
#       ;;
#   esac
#
#   _apply_overrides
#   _apply_theme&
#   _apply_bindings&
#   # shellcheck disable=SC2046
#   tmux setenv -gu tmux_conf_dummy $(printenv | grep -E -o '^tmux_conf_[^=]+' | awk '{printf "; setenv -gu %s", $0}')
#   wait
# }
#
# _urlview() {
#   tmux capture-pane -J -S - -E - -b "urlview-$1" -t "$1"
#   tmux split-window "tmux show-buffer -b urlview-$1 | urlview || true; tmux delete-buffer -b urlview-$1"
# }
#
# _fpp() {
#   tmux capture-pane -J -S - -E - -b "fpp-$1" -t "$1"
#   tmux split-window "tmux show-buffer -b fpp-$1 | fpp || true; tmux delete-buffer -b fpp-$1"
# }
#
# "$@"
```

% SHH(1) shh Manual Page
% awol <awol@member.fsf.org>
% May 2018

# NAME

shh - The shell program helper utility

# SYNOPSIS

*shh* [*OPTIONS*] [*COMMANDS*]

# DESCRIPTION

*shh* is a small utility script used to help setup, and control working environments for shell programs. A *bash* shell program to be more specific.
*shh* is capable of handling very large programs, and while sometimes it might just be best to switch to a more \"capable\" language
when a program gets very large, *bash* seems to be a language capable of very large operations. If you need to write very large programs, in *bash*, this program
might help.\ 

The logic of *shh* is simple:\
\   \* The program is broken up into three parts - *vars*, *functions*, and an *executive*.\
\   \* A *native directory* known as the *init directory* is then created.\
\   \* The *init directory* is a *parent directory*, which contains all other parent directories.

## Terminology

*native files*
:   Files that are native to the working environment, that is, files, that are not *special files*, which only exist prior toa *merge*, and will not get merged into the *working executive* (ex: *vars* *functions*).

*vars*
:   A file containing all *ENVIRONMENT* variables, and all *common* or *global* variables, meaning all variables not contained within the *scope* of a function, or *local* variable.

*functions*
:   A file which sources all functions in order.

# WORKFLOW

   \- Start a new working environment in the current directory with *init*.\
   \- Use *af* or *ae* to add new functions, or non-local variables, respectively

# OPTIONS

-s, \--silent
:   Do not prompt the user for anything (Suppresses all stdout).

-h, \--help
:   Display usage information. Use *-h* for short usage information, *\--help* for long usage information.

-v, \--version
:   Display version information. *-v* shows short information, while *\--version* displays long version information.

\--licence
:   Display licensing and copyright information.

\--warranty
:   Display warranty information.

# COMMANDS

new
:   Create a new working directory. The user is prompted to name the future executive, unless a name is supplied by *-n* or *\--name=*.

del
:   Delete all working files created, while still leaving all other files in the current directory intact.

lv
:   List variables stored in *vars*.

lf
:   List and index all functions stored in *functions*.

merge
:   Compile all working files together, based on function index. *Special files* will also be checked, and handled. By the end of the "compilation" process,
all working files should be merged into one working executive.

# SEE ALSO

gnu <https://gnu.org>, fsf <https://fsf.org>

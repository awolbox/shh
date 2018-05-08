% SHH(1) shh Manual Page
% awol <awol@member.fsf.org>
% May 2018

# NAME

shh - The shell program helper utility

# SYNOPSIS

*shh* [*OPTIONS*]... [*COMMAND*] [*COMMAND OPTIONS*]...

# NOTES

native files: *vars* *functions*

# DESCRIPTION

*shh* is a small utility script used to help setup, and control new working environments. 
These working environments are of assumed to be shell program, a *bash* shell to be more specific.
*shh* is capable of handling very large programs, and while sometimes it might just be best to switch to a more "capable" language
when a program gets very large, *bash* seems to be a language capable of very large programs.\ 

The logic of *shh* is simple:\
\    \* The program is given a primary name (*EXECUTIVE*).\
\    \* The files *functions* and *vars* are created inside the working directory.\
\    \* Another file is created, named after *EXECUTIVE*, is marked executable, and is open up on a text editor.

# WORKFLOW

   \- All *ENVIRONMENT* variables, and other commmon variables with a large scope, go in the *vars* file.\
   \- All functions are to be prefixed with the character "*\_*".

# OPTIONS

-h, \--help
:   Show usage information. Use *-h* for short usage information, *--help* for long usage information.

-v, \--version
:   Show version information. *-v* shows short information, while *--version* displays long version information.

-s, \--silent
:   Do not prompt the user for anything (Suppresses all stdout).

# COMMANDS

new
:   Create a new working directory. The user is prompted to name the future executive, unless a name is supplied by *-n* or *--name=*.

del
:   Delete all working files created, while still leaving all other files in the current directory intact.

lv
:   List variables stored in *vars*.

lf
:   List and index all functions stored in *functions*.

merge
:   Compile all working files together, based on function index. *Special files* will also be checked, and handled. By the end of the "compilation" process,
all working files should be merged into one working executive.

# COMMAND OPTIONS

-n, \--name=*EXECUTIVE*
:   Supply a name for your program. *EXECUTIVE* will be recognized as that name.

# SEE ALSO

gnu <https://gnu.org>, fsf <https://fsf.org>

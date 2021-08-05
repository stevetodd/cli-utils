# cli-utils

A small collection of scripts that I've collected over time that I've either created or modified
based on stuff I've found across the internet. I've made no effort to make these polished or
bug-free, but if you find an issue and want to contribute back PRs are welcome. I probably won't
pay much attention to issues.

## `echo-cert HOST[:PORT]`

Connects to the host and port provided as an argument and prints out the metadata of the certificate 
that is given. Default PORT is 443.

## `http-cat [PORT]`

Listens to HTTP requests and prints the headers and body to STDOUT. If the content type is 
parsable by Pygments, it will format and color the request body.

## `inall` and `in`

### `inall COMMAND [ARGS ...]`

Sometimes you run the same command in multiple directories. For example, you might be making 
changes to multiple git projects at the same time and need to get the commit status. If you have
each of the repo directories in the same parent directory, simply run `inall git status`.

This command has the added capability to read directory names from STDIN, in case you either want
to selectively choose the directories or want to modify the order in which the command is run.

### `in DIR COMMAND [ARGS ...]`

Sometimes you are doing a lot of work out of a parent directory and it sucks to do
`cd dir; foo; cd ..` a lot. This command simplifies the process to `in dir foo`.

### Caveats

Unfortunately, you can't use aliases from your shell script. If you know how to do that, I'd love
a pull request :).

## `mac-flush-dns`

Utility that flushes DNS on MacOS. I always forget the command so I just "documented" it in a small
shell script.

## `whatsmyip` and `whatsmyip6`

Automates connecting to a remote site to retrieve IPv4 and IPv6 addresses, each command respectively.


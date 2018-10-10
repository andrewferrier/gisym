# gisym

A simple set of bash functions to canonically (re)create symlinks. This is useful, for example, to keep your dotfiles in a shared git repo, and create symlinks to files in or directories in there from your home directory. Functions available are:

* `check-symlink $SOURCE $TARGET` - will create a symlink from `$SOURCE` to `$TARGET`, if the `$SOURCE` file is not already present. If it is and it is a symlink, it'll be deleted and recreated to point to `$TARGET`, use appropriate relative paths for succinctness. If it exists but is not a symlink, the function will error and exit to avoid losing data.

* `check-symlink-if-targetdir $SOURCE $TARGET` - same as above, but only if `$TARGET` exists as a directory. If not, `check-stale-link` will be run for `$SOURCE`.

* `check-symlink-if-targetfile $SOURCE $TARGET` - same as above, but only if `$TARGET` exists as a regular file. If not, `check-stale-link` will be run for `$SOURCE`.

* `check-symlink-if-command $COMMAND $SOURCE $TARGET` - same as above, but only if `$COMMAND` is an executable command. If not, `check-stale-link` will be run for `$SOURCE`.

* `check-symlink-if-directory $DIR $SOURCE $TARGET` - same as above, but only if `$DIR` exists as a directory. If not, `check-stale-link` will be run for `$SOURCE`.

* `check-stale-link $LINK` - if `$LINK` exists as a symlink, delete it.

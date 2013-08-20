## Clojure test mode pack for Emacs Live

This isn't pulled into emacs live by default. It's a very simple pack - all 
it does is require clojure-test-mode which already sits in the clojure-mode 
pack by default

To install:

    cd ~/.live-packs
    git clone git@github.com:xavriley/clojure-test-mode-pack.git

Then add the following to `~/.emacs-live.el`

    (live-add-packs '( ~/.live-packs/clojure-test-mode-pack))

## Explanation of User Pack Template

This is a template for your own user (or other purpose) pack.

### init.el

Use the file `init.el` for your own configuration elisp. If this starts
getting unwieldy then you might want to break out the config into
separate files which you can store in the config directory.

### config

Files placed in the `config` dir may then be referenced and pulled into
your `init.el` via the fn `live-load-config-file`. For example, if you
have the file config/foo.el then you may load it in with:

    (live-load-config-file "foo.el")

### lib

 If you want to pull in external libraries into your pack, then you
 should place the libraries within the lib dir. To add a directory
 within the pack's lib directory to the Emacs load path (so that it's
 contents are available to require) you can use the fn
 `live-add-pack-lib`. For example, if you have the external library bar
 stored in lib which contains the file `baz.el` which you wish to
 require, this may be achieved by:

    (live-add-pack-lib "bar")
    (require 'baz)

 Have fun!

# bash-liberror

A Bash library for error messages printing

Install
-------

You can clone this repository or download it as a zip file. To clone:

    git clone https://github.com/david-moreno/bash-liberror.git
    cd bash-liberror
    sudo make install

Uninstall
---------

Using the cloned/unzipped directory:

    cd bash-liberror
    sudo make uninstall

Usage
-----

#### err_set_values *messages*
Sets the error messages

#### err_set_keys *keys*
Sets the keys for the error messages

#### err_get_value *key*
Returns the corresponding message from *key*

#### err_print_error *key*
Prints an error message to stderr

#### err_print_warning *key*
Prints a warning message to stderr

#### err_print_fatal *key*
Prints a fatal error message to stderr

Example
-------

```bash
#!/bin/bash

#Includes the library into the script
source "/usr/lib/bash/liberror"

#Sets the error messages
err_set_values "vim not installed"\
	"MacOS is installed"\
	"Windows is installed"

#Sets the keys
err_set_keys VIM\
	MACOS\
	WINDOWS

err_print_error VIM
err_print_warning MACOS
err_print_fatal WINDOWS
```

The output on stderr is:

    ERROR: vim not installed
    WARNING: MacOS is installed
    FATAL: Windows is installed

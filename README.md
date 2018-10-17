# eslogger
Small file to including with comfortable to using logging functions

### Usage
```bash
#!/bin/sh

# Including
. ./eslogger

# Default loglevel is info, so this parameter is not necessary to
# define. If you append check for variable LOGLEVEL is exists, 
# you can start main script with different log levels by
# running it as: LOGLEVEL=info ./test.sh
# In this case I place here debug level.
[ -z "$LOGLEVEL" ] && LOGLEVEL='debug'

# Date format. Also not necessary to define. Below it defined as
# default.
[ -z "$LPREF" ] && LPREF='date +%Y.%m.%d-%H:%M:%S'

# If you hasn't tput binary for checking widht of screen in
# columns, you can place columns number here. It's needed for
# calculate divider lenght.
DEFAULT_COLS=70

# Log coloring (0/1 соответственно)
[ -z "$LCOLOR" ] && LCOLOR=1

# So, here we'll write out all of message types:
d # The d for divider
l d "This is debug message"
l i "This is info message"
l "This is also info message"
l n "This is notice message"
l w "This is warning message"
l e "This is error message"
l f "This is fatal message"
# If you need to exit immideately after fatal message, you can
# use "fe" type of message and third parameter should be exit code.
# If you wouldn't define third parameter, exit code=1 will be used
# as default. Also after message with fe type message about
# cancelling all next operations will be printed.
l fe "This is fatal message with exit code" 127
```

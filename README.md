# IRC Log Converter

## Why

We log [#HSBNE](irc://irc.freenode.net/hsbne) to file publically, as it states
in our channel topic. At one point we had to migrate logging bots due to a member
leaving. This script converts the old logs to the new logs.

The script is recorded here in case it's found in the future that some huge gaff
has been made and data lost.

## Requirements

- >= PHP5.3

## Setup

```bash
tar -xf logs.tar logs
```

## Usage

```bash
chmod +x convertphp
./convertphp
```
## Implementation Notes

The script recurses for all files, then parses out the filename and each line 
of each file to find timestamp information and consequent info like username, 
action etc. It places this all into a big array and then writes it out. Ie its
a functional piece of code, not an efficient piece of code.

If it's found to have lost any lines, then they weren't matched by $searches. Just
add a new search regex and a matching result string to transform it to. If it's
any more broken than that, you'll probably have to start from scratch cos this 
script won't help.

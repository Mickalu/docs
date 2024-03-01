for motion function to function
```
]m                      Go to [count] next start of a method (for Java or
                        similar structured language).  When not before the
                        start of a method, jump to the start or end of the
                        class.  When no '{' is found after the cursor, this is
                        an error.  |exclusive| motion.
                                                *]M*
]M                      Go to [count] next end of a method (for Java or
                        similar structured language).  When not before the end
                        of a method, jump to the start or end of the class.
                        When no '}' is found after the cursor, this is an
                        error. |exclusive| motion.
                                                *[m*
[m                      Go to [count] previous start of a method (for Java or
                        similar structured language).  When not after the
                        start of a method, jump to the start or end of the
                        class.  When no '{' is found before the cursor this is
                        an error. |exclusive| motion.
                                                *[M*
[M                      Go to [count] previous end of a method (for Java or
                        similar structured language).  When not after the
                        end of a method, jump to the start or end of the
                        class.  When no '}' is found before the cursor this is
                        an error. |exclusive| motion.
```

# Marks
```
1. With ` (backtick):     The cursor is positioned at the specified location
                          and the motion is |exclusive|.
2. With ' (single quote): The cursor is positioned on the first non-blank
                          character in the line of the specified location and
                          the motion is linewise.

                                                *m* *mark* *Mark*
m{a-zA-Z}               Set mark {a-zA-Z} at cursor position (does not move
                        the cursor, this is not a motion command).

                                                *m'* *m`*
m'  or  m`              Set the previous context mark.  This can be jumped to
                        with the "''" or "``" command (does not move the
                        cursor, this is not a motion command).

                                                *m[* *m]*
m[  or  m]              Set the |'[| or |']| mark.  Useful when an operator is
                        to be simulated by multiple commands.  (does not move
                        the cursor, this is not a motion command).

                                                *m<* *m>*
m<  or  m>              Set the |'<| or |'>| mark.  Useful to change what the
                        `gv` command selects.  (does not move the cursor, this
                        is not a motion command).
                        Note that the Visual mode cannot be set, only the
                        start and end position.

```

# Motion last time 

```
'<  `<                  To the first line or character of the last selected
                        Visual area in the current buffer.  For block mode it
                        may also be the last character in the first line (to
                        be able to define the block).

                                                        *'>* *`>*
'>  `>                  To the last line or character of the last selected
                        Visual area in the current buffer.  For block mode it
                        may also be the first character of the last line (to
                        be able to define the block).  Note that 'selection'
                        applies, the position may be just after the Visual
                        area.

                                                        *''* *``*
''  ``                  To the position before the latest jump, or where the
                        last "m'" or "m`" command was given.  Not set when the
                        |:keepjumps| command modifier was used.
                        Also see |restore-position|.

                                                        *'quote* *`quote*
'"  `"                  To the cursor position when last exiting the current
                        buffer.  Defaults to the first character of the first
                        line.  See |last-position-jump| for how to use this
                        for each opened file.
                        Only one position is remembered per buffer, not one
                        for each window.  As long as the buffer is visible in
                        a window the position won't be changed.

                                                        *'^* *`^*
'^  `^                  To the position where the cursor was the last time
                        when Insert mode was stopped.  This is used by the
                        |gi| command.  Not set when the |:keepjumps| command
                        modifier was used.

                                                        *'.* *`.*
'.  `.                  To the position where the last change was made.  The
                        position is at or near where the change started.
                        Sometimes a command is executed as several changes,
                        then the position can be near the end of what the
                        command changed.  For example when inserting a word,
                        the position will be on the last character.
                        To jump to older changes use |g;|.

```



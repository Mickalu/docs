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

## Man pages categories

| manpage section | description |
| --------------- | ----------- |
| 1               | Executable shell commands |
| 2               | System calls (kernel) |
| 3               | Library calls |
| 4               | Special files (eg /dev) |
| 5               | File formats and convetions |
| 6               | Games |
| 7               | Misc |
| 8               | System administration commands |
| 9               | Kernel routines |

`man 7 mdoc`

## Formatting man pages (troff-based)

Comments: `.\" my comment`

Header: `.SH my header`

Table header: `.TH man 8 "8-4-2018" "1.0" "example"`

Example:

    .TH man 8 "2018-04-08" "1.0" "example"
    .SH NAME
    example \- Fake example command for man-page-creation reasons
    .SH SYNOPSIS
    example [USERNAME]
    .SH DESCRIPTION
    Just a dummy non-existent command. I just want the man page.
    .SH OPTIONS
    Options go here.
    .SH SEE ALSO
    useradd(8), passwd(5), nuseradd.debian(8) 
    .SH BUGS
    No known bugs.
    .SH AUTHOR
    My Name (my.name@example.com)

Result:

    man(8)                                                                example                                                               man(8)

    NAME
            example - Fake example command for man-page-creation reasons

    SYNOPSIS
            example [USERNAME]

    DESCRIPTION
            Just a dummy non-existent command. I just want the man page.

    OPTIONS
            Options go here.

    SEE ALSO
            useradd(8), passwd(5), nuseradd.debian(8)

    BUGS
            No known bugs.

    AUTHOR
            My Name (my.name@example.com)

    1.0                                                                 2018-04-08                                                              man(8)


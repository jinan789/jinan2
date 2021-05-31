---
layout: default1
title: 'Question 4: Vega'
nav_order: 40
---

# Vega (Launched 1999)
{: .no_toc }

_Password:_ whyishould

{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Starter files

The `exploit` script in this question is slightly different. The output
of `egg` is used as an *environment variable*, which means its value is
placed at the top of the stack. The output of `arg` is used as the input
to the program.

------------------------------------------------------------------------

## Tips

-   It might help to read Section 10 of ["ASLR Smack & Laugh Reference"
    by Tilo
    Müller](http://www.icir.org/matthias/cs161-sp13/aslr-bypass.pdf).
    (ASLR is disabled for this question, but the idea of the exploit is
    similar.)

-   It might also help to read Section 2.5 (off-by-one vulnerabilities)
    of [the memory safety
    notes](https://cs161.org/assets/notes/memory-safety.pdf).

-   Environment variables are stored at the special pointer variable
    `*((char **)environ)`. To see the address of environment variables
    in gdb, you can run

            (gdb) x/2wx *((char **)environ)
            (gdb) x/2wx *((char **)environ+1)
            (gdb) x/2wx *((char **)environ+2)

-   It may take some trial-and-error to find the output of `egg` among
    the environment variables. One way to confirm you have the right
    address is to run `x/2wx [your address]` and check that gdb displays
    what you put in `egg`.

-   There is a slight chance (1 in 256) that your VM customization
    causes the value of the sfp to end in `\x00`, which makes this
    question much harder to solve. You can resolve this by printing out
    extra garbage bytes in your `egg` script (after whatever you were
    printing before), which pushes the rest of the stack to different
    addresses.

------------------------------------------------------------------------

## Deliverables
Two scripts (`egg` and `arg`) and a
[writeup](#sec:writeup). Make sure the scripts work by running
`./exploit`.


---
layout: default1
title: 'Question 2: Spica'
nav_order: 30
---

# Spica (Launched 1977)
{: .no_toc }

_Password:_ alanguage

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

Log into the `spica` account on the VM using the password you learned in
the previous question. `ls` to see the starter files.

`telemetry` is the vulnerable C program in this question. It takes a
file and prints out its contents, but it expects the file to be
specially formatted: the first byte of the file specifies its length,
followed by the actual file.

The starter files contain a small helper script
`generate-file-contents`. This script takes arbitrary input and outputs
the first 127 bytes in the format that `telemetry` expects:

``` {commandchars="\\\\\\{\\}"}
# Example invocation:
$ ./generate-file-contents < \exampleinput.txt
```

This helper script always generates safe files to be used with the
`telemetry` program, but nothing prevents you from instead feeding
`telemetry` an arbitrary file of your choice.

------------------------------------------------------------------------

## Your task

`exploit` takes the output of your `egg` script, saves it in a file, and
then uses that file as input to `telemetry`. In other words, when
`telemetry` calls `fread`, it reads from the output of your `egg`
script.

------------------------------------------------------------------------

## Debugging

No input and output redirection needed for this question.
`debug-exploit` automatically feeds the output of your `egg` script into
the C program. You can start running the program in gdb with just `run`
or `r`.

------------------------------------------------------------------------

## Deliverables
A script `egg` and a [writeup](#sec:writeup). Make
sure the script works by running `./exploit` and checking that you are
able to run `cat README` and see the next password.


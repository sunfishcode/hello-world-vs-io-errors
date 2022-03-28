# Hello World vs. I/O errors

In some programming languages, the "Hello, World!" tutorial programs report I/O
errors in their exit status. In others, they silently swallow I/O errors, which
doesn't satisfy common expectations of command-line programs.

Hello world programs are just toy examples. And, most languages do have ways to
detect I/O errors on standard output. So, this page is effectively about
defaults and ergonomics, in a specific context.

See also [the original blog post] for more discussion.

## Languages with the bug

| Language   |  Notes                                     | How to fix the bug
| ---------- | ------------------------------------------ | -----------------------------
| C          | The C standard specifies this behavior     | [Example](Examples.md#C)
| C++        | The C++ standard specifies this behavior   |
| Crystal    | `Crystal 1.3.2 (2022-01-19)`               |
| Fortran    | `GNU Fortran 11.2.0`                       |
| Go         | https://news.ycombinator.com/item?id=30612821 |
| Haxe/HashLink| `Haxe 4.2.4 + HashLink 1.11.0`           |
| Haskell    | `The Glorious Glasgow Haskell Compilation System, version 8.8.4` |
| Java       | This is [documented behavior in Java], [since Java 1.0] |
| Julia      | https://news.ycombinator.com/item?id=30619661 |
| Nim        | `Nim Compiler Version 1.6.4`               |
| Node.js    | `v12.21.0`                                 |
| Pascal     | https://news.ycombinator.com/item?id=30613381 |
| Python 2   | `Python 2.7.18`                            |
| Ruby       | `ruby 2.7.2p137 (2020-10-01 revision 5445e04352) [x86_64-linux-gnu]` |
| Scheme     | `CHICKEN 5.2.0`                            |
| Swift      | `Swift version 5.5.3`                      |

## Languages without the bug

| Language   | Notes
| ---------- | ---------------
| Ada        | `GNAT 10.3.0`
| Awk        | `GNU Awk 5.1.0, API: 3.0 (GNU MPFR 4.1.0, GNU MP 6.2.1)`
| Bash       | `GNU bash, version 5.1.4(1)-release (x86_64-pc-linux-gnu)`
| C#         | `Mono JIT compiler version 6.8.0.105`
| Deno       | `deno 1.11.0 (release, x86_64-unknown-linux-gnu)`
| Hack       | `HHVM 4.108` or above when using [HSL IO]
| Lisp       | `SBCL 2.1.1`
| OCaml      | `4.08.1`
| Perl       | `perl 5, version 32, subversion 1 (v5.32.1) built for x86_64-linux-gnu-thread-multi (with 46 registered patches...)`
| Perl 6     | `v2020.12`
| Php        | `PHP 8.0.8 (cli) (build: Mar  3 2022 14:51:53) ( NTS )`
| PowerShell | https://twitter.com/perostergaard/status/1501936409547993102
| Python 3   | `Python 3.9.5`
| Racket     | `Racket v7.9 [bc]`
| Rust       | This is [documented behavior in Rust].
| Tcl        | `8.6.11`
| Zig        | https://ziglang.org/documentation/master/#Hello-World

The specific source code tested comes from doing simple Web searches for
hello world programs. The intention is to test the programs that are presented
to newcomers, and not programs specifically written to fix this bug.

In some cases, only a specific implementation has been tested, and it's not yet
been determined what the actual documented or specified behavior is. In those
cases, I've listed the versions tested, or links to reports.

Node.js (and Deno) is listed here as a "Language" because JavaScript itself doesn't have
a builtin concept of standard output, so it takes an embedding like Node.js to
connect JS features to command-line concepts such as standard output.

PRs adding more languages, more information about existing languages, updates,
or corrections are welcome!

[documented behavior in Java]: https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/io/PrintStream.html
[since Java 1.0]: http://web.mit.edu/java_v1.0.2/www/javadoc/java.io.PrintStream.html#checkError()
[documented behavior in Rust]: https://doc.rust-lang.org/stable/std/macro.println.html#panics
[Wikipedia's list of "Hello, World!" programs]: https://en.wikipedia.org/wiki/%22Hello,_World!%22_program#Examples
[The Hello World Collection]: http://helloworldcollection.de/
[the original blog post]: https://blog.sunfishcode.online/bugs-in-hello-world/
[HSL IO]: https://docs.hhvm.com/hack/getting-started/input-and-output

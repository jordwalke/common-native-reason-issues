# Common Issues When Developing Native Reason Projects

**Symptom:**
When building your app you see a bunch of errors like:
/usr/bin/ld: /home/you/.esy/3______________________________________________________________________/i/ocaml-4.9.1000-ffe51dac/lib/ocaml/libasmrun.a(roots_nat_n.o): relocation R_X86_64_32 against symbol `caml_frametable' can not be used when making a PIE object; recompile with -fPIE
/usr/bin/ld: /home/you/.esy/3______________________________________________________________________/i/ocaml-4.9.1000-ffe51dac/lib/ocaml/libasmrun.a(major_gc_n.o): relocation R_X86_64_32 against `.rodata.str1.1' can not be used when making a PIE object; recompile with -fPIE
/usr/bin/ld: /home/you/.esy/3______________________________________________________________________/i/ocaml-4.9.1000-ffe51dac/lib/ocaml/libasmrun.a(minor_gc_n.o): relocation R_X86_64_32 against `.rodata.str1.1' can not be used when making a PIE object; recompile with -fPIE
/usr/bin/ld: /home/you/.esy/3______________________________________________________________________/i/ocaml-4.9.1000-ffe51dac/lib/ocaml/libasmrun.a(memory_n.o): relocation R_X86_64_32 against symbol `caml_ref_table' can not be used when making a PIE object; recompile with -fPIE

**Problem:**
It is likely that your gcc is too old and it doesn't work well with the specific version of OCaml you are using.
What does `which gcc` pick up in your path? What is its version.
In your project what does `ocaml -version` report?
OCaml 4.9 has been known to have problems with really old gcc versions.

**Solution:**
Upgrade your ocaml in your `package.json` to 4.10.

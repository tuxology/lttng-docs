---
id: lttng-gen-tp
---

LTTng-UST ships with `lttng-gen-tp`, a handy command line utility for
generating most of the stuff discussed above. It takes a _template file_,
with a name usually ending with the `.tp` extension, containing only
tracepoint definitions, and outputs a tracepoint provider (either a C
source file or a precompiled object file) with its header file.

`lttng-gen-tp` should suffice in [static linking](#doc-static-linking)
situations. When using it, write a template file containing a list of
`TRACEPOINT_EVENT()` macro calls. The tool will find the provider names
used and generate the appropriate files which are going to look a lot
like `tp.h` and `tp.c` above.

Just call `lttng-gen-tp` like this:

<pre class="term">
lttng-gen-tp my-template.tp
</pre>

`my-template.c`, `my-template.o` and `my-template.h` will be created
in the same directory.

For more information on `lttng-gen-tp`, see
<a href="/man/1/lttng-gen-tp" class="ext">its manpage</a>.

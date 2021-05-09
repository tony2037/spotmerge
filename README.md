# spotmerge
Use kprobe to observe how block io merge works

# How does it work?
* Use kprobe to pre-hook `elv_merge`
* Use `dump_stack()` to observe stack frame
* Use register `dx` which points to the third argument `struct *bio`, then dump info we are curious about

# Reference
* [Linux document for kprobes](https://www.kernel.org/doc/html/latest/trace/kprobes.html)
* [kprobe structure](https://elixir.bootlin.com/linux/latest/source/include/linux/kprobes.h#L62)
* [ptregs structure](https://elixir.bootlin.com/linux/v5.8/source/arch/x86/include/asm/ptrace.h#L12)
* [block merge queue scheduler](https://elixir.bootlin.com/linux/v5.8/source/block/blk-mq-sched.c#L295)
* [kallsyms: new /proc/kallmodsyms with builtin modules and symbol sizes](https://lwn.net/Articles/804850/)

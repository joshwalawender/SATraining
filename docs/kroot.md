# KROOT

Typically, core instrument software is located in "kroot" which is usually located or linked at `/kroot` on the instrument computers.  All the "released" (compiled) code specific to the instrument is there.  There are exceptions however, some instruments have scripts in the `bin` directory on the eng account or sometimes another account.  A few scripts common to multiple instruments may be located on a shared directory in `/sol/apps/kroot/summit/instr/bin` (or other symlinked names).

The released code will typically be in `/kroot/rel` and its subdirectories. Where source code lives can vary from instrument to instrument.  One pattern which exists is to have either (or both) `dev` and `bld` accounts which have their own `kroot` (typically in their home directories) and which have a `src` subdirectory under that `kroot`.  When the software is "released", the new code in the `src` directory is compiled (if necessary) and then copied to the `/kroot/rel` directory which all account see.

There is variation in the release process, but the basic ideas described here should help you begin to navigate the source code.

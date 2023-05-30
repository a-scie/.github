# The Science Projects

The Science projects help you package your interpreted applications as native executables.

These native executables are called scies (pronounced "skis") and generally include both a native
interpreter and your interpreted application code. Scies are built using a manifest you write that
describes the files to include n the scie as well as the commands to run when executing the scie.
Scies boot with the `scie-jump` native executable which inspects the environment, the command line
arguments and the manifest contained in the scie to determine which commands to run and which files
they need. The `scie-jump` then extracts the required files if needed and executes the required
commands.

You likely want to get started with `science`, the high-level tool for building scies that is
itself a scie built using `science`:
* Documentation: https://science.scie.app/
* Code: https://github.com/a-scie/lift

You can use the `scie-jump` directly to build scies, but it's more low-level than `science`. The
core environment variables and placeholders that power scie commands are all defined and implemented
by the `scie-jump` though; so its good to become familiar with these in its packaging docs:
* Documentation: https://github.com/a-scie/jump/blob/main/docs/packaging.md
* Code: https://github.com/a-scie/jump

Scies have the ability to be shipped "gouged-out". One or more files can be defined in the manifest
that are fetched on-demand and verified against a checksum. The `ptex` binary does this fetching and
fills the gouged-put scie back in:
* Code: https://github.com/a-scie/ptex


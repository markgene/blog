---
title: Install Entrez Direct on MacOS
author: Mark
date: '2019-05-31'
slug: install-entrez-direct-on-macos
categories:
  - Bioinformatics
tags:
  - Entrez
  - edirect
  - eutilities
description: ''
thumbnail: ''
---

I install Entrez Direct following the [instruction at the official website](https://www.ncbi.nlm.nih.gov/books/NBK179288/) and [The Insider's Guide to Accessing NLM Data](https://dataguide.nlm.nih.gov/edirect/install.html), instead of `homebrew`, because I do not have a simple solution for the error message like

```sh
Parser.c: loadable library and perl binaries are mismatched (got handshake key 0xdb00080, needed 0xdb80080)
```

FYI, I tried the solutions in [a discussion in StackOverflow](https://stackoverflow.com/questions/45000585/listutil-c-loadable-library-and-perl-binaries-are-mismatched-got-handshake-key), but it did not work for me.

---

Install Entrez Direct with `homebrew`. It is not in the core but in `brewsci/bio`:

```sh
brew tap brewsci/bio
brew search edirect
brew install brewsci/bio/edirect
```

Follow the instruction in the installation process. Below is what I got.

```sh
==> Caveats
==> openssl
A CA file has been bootstrapped using certificates from the SystemRoots
keychain. To add additional certificates (e.g. the certificates added in
the System keychain), place .pem files in
  /usr/local/etc/openssl/certs

and run
  /usr/local/opt/openssl/bin/c_rehash

openssl is keg-only, which means it was not symlinked into /usr/local,
because Apple has deprecated use of OpenSSL in favor of its own TLS and crypto libraries.

If you need to have openssl first in your PATH run:
  echo 'export PATH="/usr/local/opt/openssl/bin:$PATH"' >> ~/.bash_profile

For compilers to find openssl you may need to set:
  export LDFLAGS="-L/usr/local/opt/openssl/lib"
  export CPPFLAGS="-I/usr/local/opt/openssl/include"

==> perl
By default non-brewed cpan modules are installed to the Cellar. If you wish
for your modules to persist across updates we recommend using `local::lib`.

You can set that up like this:
  PERL_MM_OPT="INSTALL_BASE=$HOME/perl5" cpan local::lib
  echo 'eval "$(perl -I$HOME/perl5/lib/perl5 -Mlocal::lib=$HOME/perl5)"' >> ~/.bash_profile
```
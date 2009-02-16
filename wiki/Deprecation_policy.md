---
title: Deprecation policy
permalink: wiki/Deprecation_policy
layout: wiki
---

As bioinformatics and computational biology are developing quickly, some
of previously developed Biopython modules may no longer be relevant in
today's world. To keep the code base clean, we aim to deprecate and
remove such code from Biopython, while avoiding any nasty surprises for
users who may be relying on older code.

This is the (unofficial) policy for deprecating and removing code from
Biopython:

-   First, it is a good idea to ask on the biopython and biopython-dev
    mailing lists whether a given piece of code has any users. Please
    keep in mind that not all users are following the biopython-dev
    mailing list.
-   If there are no apparent users, you can add a DeprecatingWarning to
    the code.

`import warnings`  
`warnings.warn("""\`  
`Bio.SomeModule has been deprecated, and we intend to remove it in a future release of Biopython. Please use the SomeOtherModule instead, as described in the Tutorial. If you would like to continue using Bio.SomeModule, please contact the Biopython developers at biopython-dev@biopython.org""",`  
`             DeprecationWarning)`

-   In principle, we require that two Biopython releases carrying the
    deprecation warning are made before the code can be
    actually removed.
-   In addition, at least one year should pass between the first
    Biopython release carring the deprecation warning, and the first
    Biopython release in which the code has been actually removed.

See here for the discussion on the mailing list:

<http://lists.open-bio.org/pipermail/biopython-dev/2008-November/004920.html>
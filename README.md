evlang
======

Note - unworking, experimental code. 

This was a proof of concept "stripped-down" Python implementation. Its
purpose was to allow for users of the
[Evennia](https://github.com/evennia/evennia)
MUD design system to execute unsafe Python-like code in a safe way. It
was since removed from the Evennia distribution since 

1. It does not work anymore
1. It has at least one exploitable security hole: `a=[1];[a.append(x) for x in
a]`. This will cause an infinite loop that eats all memory and there
is nothing the system can do to stop it - even when using Process
offloading. 
1. We felt that we didn't want to lure people into thinking this is a 
safe thing to use. 

So, to be clear - this is not intended to be pulled and used off the bat. Its
main use is to get ideas and for reference (and for users of Evennia who wonders
where it went); Evlang uses a conglomerate of whitelist- 
and blacklist techniques as well as asp introspection to try to limit the 
Python language to something crippled but safer. And whereas we
don't quite succeed in a supportable way it may be interesting for
reference.

Read `evennia_related/README` for the original disclaimer and technical
info about Evlang published with Evennia.

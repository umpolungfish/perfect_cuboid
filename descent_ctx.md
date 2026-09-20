A perfect cuboid is a box with integer edges a,b,c, integer face diagonals
d,e,f, and integer space diagonal g, satisfying:
  a^2 + b^2 = d^2
  a^2 + c^2 = e^2
  b^2 + c^2 = f^2
  a^2 + b^2 + c^2 = g^2
No perfect cuboid is known; whether one exists is open.

The non-existence proof under construction uses infinite descent on g. Three
cases exhaust every primitive cuboid:
  A. g even -> all seven entries even -> halve -> a strictly smaller cuboid.
     PROVEN (halve_g_smaller, axiom-clean).
  B. gcd(a,b)=gcd(a,c)=gcd(b,c)=1 -> parity contradiction mod 4. PROVEN
     (case_all_gcd_one_impossible, axiom-clean).
  C. g odd and some edge-pair shares a factor. THE RESIDUAL.

Already proven for case C (axiom-clean, mod 4): exactly one of a,b,c is odd.
So WLOG c odd, a,b even.

The descent needed: from a case-C cuboid, construct a STRICTLY SMALLER cuboid
in the same set, so infinite descent forces the set empty. The obstruction is
that the two even edges share structure but the reduced object must satisfy all
four Diophantine constraints simultaneously, not just have a smaller diagonal.

The classical sketch (flawed): with a,b even write g via two representations as
a sum of two squares, factor c^2 = (v^2-u^2)^2 - (2pq)^2 as a difference of
squares X*Y = c^2 with d=gcd(X,Y) | pq, then subcases d=1, d=p, d=pq. That
sketch's subcase arguments do not close.

The object wanted: the map that takes a case-C perfect cuboid and returns a
strictly smaller perfect cuboid, closing the descent.

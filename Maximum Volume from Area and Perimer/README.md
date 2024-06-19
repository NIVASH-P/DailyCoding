Algorithm:

  V = l*b*h
  P = 4(l+b+h)
  A = 2(l*h+b*h+h*l)
  bh = A/2-(l*h)-(b*l)
  v = l*( A/2-(l*h)-(b*l) )
  v = l*(A/2-l*(h+b))
  b+h = P/4 - l
  v = l*(A/2-l*(P/4 - l))
  v = l*(A/2) - l*l*(P/4) + l^3

  to Differentiate to get critical point to acheive maximum area
  dV/dl = (A/2) - l*(P/4) + l^2

  solve this to get l;

  subtitute l in v



  Coding:

  class Solution {
  public:
    double maxVolume(double p, double a) {
        // code here
        double l = (p - sqrt((p*p)-(24*a)))/12;
        double v = l*(a/2.0) - ((l*l*p)/4.0) + l*l*l;
        return v;
    }
};

  

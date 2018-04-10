
Test 1: 
For a given declaration of a class, write the correspond .cpp file.

* Velocity is described as a polynomial v(t) from 0s to terminal_tau. Polynomial coefficients are given by vel_coeff
* We assume that after terminal_tau velocity remains stable
* S(0) = 0


piece_wise_function.hpp
```c++
class PieceWiseFunction {
public:
    PieceWiseFunction(const std::vector<double> &vel_coeff, const double &terminal_tau);
    double getS(double t);
    double getVel(double t);
    double getAcc(double t);
    double getJerk(double t);


private:
    double terminal_tau_;
    std::vector<double> vel_coeff;
    



}

```
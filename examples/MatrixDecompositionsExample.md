```java


import static org.math.array.LinearAlgebra.*;
 
import org.math.array.linearalgebra.*;
 
public class MatrixDecompositionsExample {
        public static void main(String[] args) {
 
                // random 4 x 4 matrix + Id
                double[][] A = plus(random(4, 4), identity(4));
                
                // Eigen values Decomposition : A = V * D * V^-1
                EigenvalueDecomposition eig = eigen(A);
 
                double[][] V = eig.getV();
                double[][] D = eig.getD();
 
                // Cholesky Decomposition : A = Lc * t(Lc)
                CholeskyDecomposition chol = cholesky(A);
 
                double[][] Lc = chol.getL();
 
                // LU Decomposition : A = L * U
                LUDecomposition lu = LU(A);
 
                double[][] L = lu.getL();
                double[][] U = lu.getU();
 
                // QR Decomposition : A = Q * R
                QRDecomposition qr = QR(A);
 
                double[][] Q = qr.getQ();
                double[][] R = qr.getR();
 
                // print matrices in command line
                System.out.println("A = \n" + tostring(A));
                System.out.println("V = \n" + tostring(V));
                System.out.println("D = \n" + tostring(D));
                System.out.println("V * D * V^-1 = \n" + tostring(times(times(V,D),inverse(V))));
                System.out.println("Lc = \n" + tostring(V));
                System.out.println("D = \n" + tostring(D));
                System.out.println("Lc * t(Lc) = \n" + tostring(times(Lc,transpose(Lc))));
                System.out.println("L = \n" + tostring(L));
                System.out.println("U = \n" + tostring(U));
                System.out.println("L * U = \n" + tostring(times(L,U)));
                System.out.println("Q = \n" + tostring(L));
                System.out.println("R = \n" + tostring(U));
                System.out.println("Q * R = \n" + tostring(times(Q,R)));
 
        }
}


```

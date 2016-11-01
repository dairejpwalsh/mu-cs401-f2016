#CS401 Machine Learning  
    
##Lecture 6

###Convergence and Gradient
****
Convergence is attempting to move towards an optimal point. This is achieved by finding a balance of values that will allow us to take the correct “steps” towards the optimal point.
To make life easy we keep everything in one dimension for the moment: 

We have an error E such that: 
        
        E = λ (½) w2

**Formula for Convergence/Gradient:**  
        
        w(t+1) =  w(t)  –  θ  ▽E  	
But:   
        
        ▽E = dE/dw = λw   
So we have:   
        
        w(t+1) =  w(t)  –  θ  λw

****


For convergence we need:    
    
        θ < 2/ λ

We now get: 
    
        w(t) = (1- θ λ)t w(0)

We are trying to get as close as possible to the optimum point, i.e. zero. (Converge on 0) As we apply the above formulas we need to take steps of appropriate size towards 0. The graph below should help to visualise movement towards the optimum point:
 
Graph1: ![Alt](\img\lecture-06\Lecture6-Image1.jpg "Graph1")
 
####**So For Instance:**

Dimension: w = n > 1

The graph below represents a valley, in reaching w* we would be reaching the optimum point:

Graph2: ![Alt](\img\lecture-06\Lecture6-Image2.jpg "Graph1")

We have the same gradient formula as above:

        w(t+1) = w(t) –  θ  ▽w E
****
*Let H = ▽w E = ▽2 E Δw  
So H = ▽2 E*
****
Now written as:
        
        w* + Δw (t+1) = w* + Δw(t) – θ H Δw(t)
        Δw (t+1) = Δw(t) – θ H Δw(t)
                 = (I - θ H) Δw(t)  	                where I = Identity matrix
        Δw (t)   = (I - θ H)t Δw(0)

Series Expansion:

        E (w*+  Δw)    =   E(w*)  +  ▽E(w*) · Δw  +  ½ ΔwT   ▽2 E Δw  +  0(||Δw||2)
        
▽E(w*) · Δw  is going to be zero, so we can ignore this:
        
        E (w*+  Δw)    =   E(w*)  +  ½ ΔwT   ▽2 E Δw  +  0(||Δw||2)
        
▽2 E is a symmetric matrix of 2nd derivative of E with respect to w known as the Hessim matrix. 

Consider the same graph again, with different labels:
 
Graph3: ![Alt](\img\lecture-06\Lecture6-Image3.jpg "Graph3")

Let c1 and c2 be Eigen vectors.
	
    H = Σi  λi  ( (c(i)  c(i)) T )
Note that:

	|| c(i) || = 1  	
And for w* to be a minimum of E 
	
    λi > 0

Now we write Δw in eigen basis:
	
       Δw = Σi   bi  c(i)  
	   b(t) = (I – θ Σi   λi  (c(i)  c(i)) T)  Σi   bi (0) c(i)  
	   b(t) = Σi (I – θ  λi ) ((c(i)  c(i)) T)  Σj   bj (0) c(j)  
	   b(t) = Σi ,j (I – θ  λi ) ((c(i)  c(i)) T)   bj (0) c(j) 
	   b(t) = Σi  (I – θ  λi )t (c(i))  (bi) (0)
	   bi(t) = (I - θ  λi)t bi (0)

For all i:

-1   <   (1- θ  λi)   <   1

But θ > 0, so:

	Θ   <   2/λi 	∀ i
	Θ   <   2/λmax





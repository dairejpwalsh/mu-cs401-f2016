NMF Documents

Tables that have words on rows and documents on columns, entires denote the number of times the word is used in the document.
Alternatively a table that shoes the star rating a person gave a movie.

````
Movies vs People
              Jaws  ...   Killer Clowns      ...
Robert        -     ...   4                  ...
...           ...   ...   ...                ...
...           ...   ...   ...                ...
Barak         4     ...   -                  ...
...           ...   ...   ...                ...
````
How can we fill in the empty entries? This would give us an estimate of a persons rating of a movie so we can suggest what movies they might want to watch next.  
Possible strategies:
* Movies average rating
* Weighted average where people that like similar movies have greater weighting


We can separate the nxm-matrix into rows and columns of people and movies. Say there is L non-missing entries  
k(n+m) = nk+mk < l << nm  
k<l/(n+m)  

![d_i](img/lecture-17/d_i.png)  
Find c1, c2, c3 such that  
![c*](img/lecture-17/c*.png)  

Bad if we want sparse c  
![argmins](img/lecture-17/argmins.png)

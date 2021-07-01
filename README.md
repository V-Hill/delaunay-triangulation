# delaunay-triangulation
This library is used for computing the [Delaunay triangulation](https://en.wikipedia.org/wiki/Delaunay_triangulation) of 2D point sets.

An example Delaunay triangulation output for 32 points is shown below.
<img src="./images/Figure 2021-02-24 110617.png" alt="drawing" width="500"/>

**Why is this library special?**

Speed! This is a pure python implemenation of the Guibas &amp; Stolfi's divide and conquer algorithm. The divide and conquer algorithm has been shown to be the [fastest](https://people.eecs.berkeley.edu/~jrs/meshpapers/SuDrysdale.pdf) DT generation technique, with O(*n* log *n*) running time. Furthermore, this code has been parallelised using the MPI for Python ([mpi4py](https://github.com/mpi4py/mpi4py)) library to utilise multiple CPU cores. This allows the algorithm to be efficiently scaled for distributed computing across supercomputer nodes.

## Structure
This repository is currently structured as follows.

    ├── delaunay_triangulation       
        ├── triangulation_core
            ├── points_tools   
                ├── generate_values.py
                └── split_list.py
            ├── edge_topology.py
            ├── linear_algebra.py
            ├── triangulation.py
            └── triangulation_primitives.py  
        ├── utilities    
            └── settings.py
        ├── triangulation_cli.py
        ├── triangulation_mpi_test.py
        └── triangulation_test.py
        
## References
<a id="1">[1]</a> 
Guibas, Leonidas and Stolfi, Jorge
'Primitives for the Manipulation of General Subdivisions and the Computation of Voronoi'
In: ACM Trans. Graph.4.2  (Apr.1985),  pp.  74–123.
issn:  0730-0301
doi:10.1145/282918.282923

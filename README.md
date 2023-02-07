# optTrees



## Usage
	./optTrees -S <file with a species tree> -G <file with a gene tree> [-D <int>, -L <int>, -o <output name> -h]

## Options
	-S <file with a species tree>
	-s <species tree string>
	-G <file with a gene tree>
	-g <gene tree string>
	-D <cost of duplication event>  -- default value: 2
	-L <cost of loss event> -- default value: 1
	-t -- save all optimal gene trees to the output file
	-m -- print heatmap results
	-o -- output file name -- default value: optTree.out
	-h -- print help

## Examples

Optimal gene trees for a given gene and species tree: 

- Basic command:
		
		./optTrees -s "((a,b),c)" -g "(a,?)" -t

- The trees given in files in  newick format:
 
		./optTrees -S data/speciestree -G data/genetree -t

- Additional parameters -D and -L change the cost of duplication and gene loss events to 3 and 0, respectively:

		./optTrees -s "((a,b),c)" -g "(a,?)" -L 0 -D 3 -t
- Additional parameter -o changes the name of the output file.

		./optTrees -s "((a,b),c)" -g "(a,?)" -o newOutputName


## Output
The output file contains the number of optimal gene trees (first line), all optimal gene trees in newick format (the following line except the last one), and the species tree (last line).

# autoALE

The python script **autoALE.py** will run the process-based cophylogenetic analysis as outlined in Satler et al. (*in press*). This approach uses the DTL model as implemented in ALE (Szollosi et al. 2013a, 2013b).

This outlines how to run ALE over a posterior distribution of host trees and symbiont trees, accounting for uncertainty in both tree distributions. If using a single host tree (i.e., MCC tree), use ALE commands as normal.  

Example data sets are available at [https://doi.org/10.5061/dryad.423q544].

___
## Instructions for use ##

I keep directory structure as follows:  

ale  
|-- data  
|   |-- Host.trees  
|   |-- Symbiont.trees  
|-- script  
|   |-- autoALE.py  
|   |-- traits.file  

From within the script directory, call **autoALE.py** to run analysis.  

usage:  
```
    python autoALE.py ../data/Host.trees ../data/Symbiont.trees traits.file dated|undated yes|no  
```
[Notes]  
-Script assumes ALE programs (ALEobserve, ALEml) are in PATH. Available from [https://github.com/ssolo/ALE].  

-The traits file contains associations between symbionts and hosts. This is a tab delimited file which has **symbiont tip [tab] host tip**. For example:  

> \#GT ST  
> symbiont1 [tab]	host1  
> symbiont2 [tab] host2  
> symbiont3 [tab]	host3  


-[dated|undated] Can run either the dated or undated version of ALE. We used dated for the paper. If using undated, have ALEml_undated available in your PATH.  

-[yes|no] Run ALE using the model selection tests as outlined in the paper. If input is yes, will run analysis on the full DTL model and all subsets of the model. If input is no (or no choice is input), will run analysis solely on full DTL model.
___

If you have any questions or comments, please feel free to email me at jordansatler@gmail.com.
___
References:

Satler, J. D., E. A. Herre, K. C. Jander, D. A. R. Eaton, C. A. Machado, T. A. Heath, and J. D. Nason. Inferring processes of coevolutionary diversification in a community of Panamanian strangler figs and associated pollinating wasps. *Evolution*, *in press*.  

Szollosi, G. J., W. Rosikiewicz, B. Boussau, E. Tannier, and V. Daubin. 2013a. Efficient exploration of the space of reconciled gene trees. *Systematic Biology*, **62**:901--912.  

Szollosi, G. J., E. Tannier, N. Lartillot, and V. Daubin. 2013b. Lateral gene transfer from the dead. *Systematic Biology*, **62**:386--397.  

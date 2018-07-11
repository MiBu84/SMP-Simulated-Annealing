# SMP-Simulated-Annealing #
Parallel Simulated Annealing approach to fit measurement points in performance model normal form (PMNF).

# Compilation #
## Build Requirements ##
* Microsoft Visual Studio 2017
* NAG C Library (CLW6I25DAL, CLW6I24DAL)
* Eigen (C++ Library) (3.3.3 or higher)
* `pdflatex` command must be available in system path
* Recommended: pdfXChange Viewer installed and available in system path

## Enable LaTeX output ##
* Jump to comment `LaTeX Config: Comment out to disable` in `SimulatedAnnealingExtraP.cpp`
* Uncomment the following two lines:

    LatexPrinter<SolutionType> latprint = LatexPrinter<SolutionType>();
    latprint.printSolution("", &abs_min_sol, inputDB, calcinf);
    
* Jump to comment `LaTeX Config: Adapt commands` in `LatexPrinter.cpp`
* Set the strings `close_command` and `open_command` to your corresponding pdf viewer
* Recompile the code


# Usage #
## Call parameters ##
* `--inputfile PATH`: Path and file with measurement data in the format as you can find them in the input folder in the repository (Default: `C:\temp`)
* `--texfile FILENAME`: Name of the pdf report and temporary LaTeX-files. Do not append a fileextension! (Default: `DefaultModel`)
* `--outpath PATH`: Folder to write the pdf report
* `--nt INTVAL`: Number of threads employed for parallel search (Default: 1)
* `--epol FLOATVAL`: Maximal exponent that is tried out for the problem size variable in the PMNF
* `--elog FLOATVAL`: Maximal exponent that is tried out for the logarithm in the PMNF

## Extended config ##
* Program defaults can be changed in `Configurator.h`


# Examples #
The folder `input` contains all primary data for the paper (n1.0fplll.txt/n1.00ntl.txt, n2.0fplll.txt/n2.0ntl.txt, ntru2fplll.txt/ntru2ntl.txt, n1.00ntlWestmere.txt/n1.00ntlFP.txt)
The folder `output` conaints some exemplary example files.
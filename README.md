# tikz-microbio
A set of tikz drawings for microbiology-related figures.

### Tikz libraries
- `\bacteria`, `\bacterium`, `\bactpattern` and `\dna` require to load the [`decoration.pathmorphing` tikz library](https://tikz.dev/tikz-decorations)
- `\bactpattern` also requires to load the [`pattern` tikz library](https://tikz.dev/library-patterns)
- `\dna` also requires to load the [`arrows` tikz library](https://tikz.dev/tikz-arrows)
- `\nowater` requires to load the [`calc` tikz library](https://tikz.dev/tikz-coordinates#tikz-lib-calc)

### Arguments
Most functions require 3 arguments:
1. a scale factor
2. a color
3. a name for the node containing the drawing (facultative)
4. the name of a [`pattern`](https://tikz.dev/library-patterns) for `\bactpattern`

### Usage

```
\path (0,0) \bacterium{0.5}{blue}{bact1};
```
The code from `tikz_drawings.tex` can be pasted into the preamble of the document, or added with the `\input{}` command (see example below).


### Example

![](example.jpg)

```
\documentclass[11pt]{standalone}                                                                                                                                                                                   
\usepackage[utf8]{inputenc}
\usepackage{tikz}                                                                                                                                                                                                  
\usetikzlibrary{arrows, patterns, decorations.pathmorphing}                                                                                                                                                  
                                                                                                                                                                                   
\input{tikz_drawings.tex}
                                                            
\begin{document}
\begin{tikzpicture}
  \path (0,0) \assembly{0.7}{violet}{a};
  \path (a.south) node[anchor=north] {\ttfamily \textbackslash assembly};

  \path (3,0) \bacteria{0.5}{teal}{b};
  \path (b.south) node[anchor=north] {\ttfamily \textbackslash bacteria};

  \path (6,0) \bacterium{0.5}{purple}{c};
  \path (c.south) node[anchor=north] {\ttfamily \textbackslash bacterium};

  \path (9,0) \bactpattern{0.5}{pink}{d}{dots}; 
  \path (d.south) node[anchor=north] {\ttfamily \textbackslash bactpattern};
                                                                                                                                       
  \path (12,0) \dna{1}{orange}{e}; 
  \path (e.south) node[anchor=north] {\ttfamily \textbackslash dna};
                                                                                                                                             
  \path (15,0) \eppendorf{1}{cyan}{f};     
  \path (f.south) node[anchor=north] {\ttfamily \textbackslash eppendorf};

  \path (0,-3) \gear{0.5}{gray}{g};                                                
  \path (g.south) node[anchor=north] {\ttfamily \textbackslash gear};
                                                                                                                                             
  \path (3,-3) \metamod{0.2}{magenta}{h}; 
  \path (h.south) node[anchor=north] {\ttfamily \textbackslash metamod};
                                                                                                                                     
  \path (6,-3) \molecule{2}{olive}{i};
  \path (i.south) node[anchor=north] {\ttfamily \textbackslash molecule};
                                      
  \path (9,-3) \nowater{0.6}{blue}{i2};
  \path (i2.south) node[anchor=north] {\ttfamily \textbackslash molecule};

  \path (12,-3) \petri{0.6}{brown}{j};                  
  \path (j.south) node[anchor=north] {\ttfamily \textbackslash petri};
                                                                                                                                    
  \path (15,-3) \tube{0.4}{lime}{k}; 
  \path (k.south) node[anchor=north] {\ttfamily \textbackslash tube};                                                                                                                                              
\end{tikzpicture}                                                                                                                                                                              
\end{document}                                         
```

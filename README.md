
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" xml:lang="en"><head>

<meta charset="utf-8">
<meta name="generator" content="quarto-1.4.555">

<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">

<meta name="author" content="Daiju Aiba">
<meta name="dcterms.date" content="2024-07-25">

<title>Tutorial of R (Docs)</title>
<style>
code{white-space: pre-wrap;}
span.smallcaps{font-variant: small-caps;}
div.columns{display: flex; gap: min(4vw, 1.5em);}
div.column{flex: auto; overflow-x: auto;}
div.hanging-indent{margin-left: 1.5em; text-indent: -1.5em;}
ul.task-list{list-style: none;}
ul.task-list li input[type="checkbox"] {
  width: 0.8em;
  margin: 0 0.8em 0.2em -1em; /* quarto-specific, see https://github.com/quarto-dev/quarto-cli/issues/4556 */ 
  vertical-align: middle;
}
/* CSS for syntax highlighting */
pre > code.sourceCode { white-space: pre; position: relative; }
pre > code.sourceCode > span { line-height: 1.25; }
pre > code.sourceCode > span:empty { height: 1.2em; }
.sourceCode { overflow: visible; }
code.sourceCode > span { color: inherit; text-decoration: inherit; }
div.sourceCode { margin: 1em 0; }
pre.sourceCode { margin: 0; }
@media screen {
div.sourceCode { overflow: auto; }
}
@media print {
pre > code.sourceCode { white-space: pre-wrap; }
pre > code.sourceCode > span { text-indent: -5em; padding-left: 5em; }
}
pre.numberSource code
  { counter-reset: source-line 0; }
pre.numberSource code > span
  { position: relative; left: -4em; counter-increment: source-line; }
pre.numberSource code > span > a:first-child::before
  { content: counter(source-line);
    position: relative; left: -1em; text-align: right; vertical-align: baseline;
    border: none; display: inline-block;
    -webkit-touch-callout: none; -webkit-user-select: none;
    -khtml-user-select: none; -moz-user-select: none;
    -ms-user-select: none; user-select: none;
    padding: 0 4px; width: 4em;
  }
pre.numberSource { margin-left: 3em;  padding-left: 4px; }
div.sourceCode
  {   }
@media screen {
pre > code.sourceCode > span > a:first-child::before { text-decoration: underline; }
}
</style>


<script src="Tutorial of R (Docs)_files/libs/clipboard/clipboard.min.js"></script>
<script src="Tutorial of R (Docs)_files/libs/quarto-html/quarto.js"></script>
<script src="Tutorial of R (Docs)_files/libs/quarto-html/popper.min.js"></script>
<script src="Tutorial of R (Docs)_files/libs/quarto-html/tippy.umd.min.js"></script>
<script src="Tutorial of R (Docs)_files/libs/quarto-html/anchor.min.js"></script>
<link href="Tutorial of R (Docs)_files/libs/quarto-html/tippy.css" rel="stylesheet">
<link href="Tutorial of R (Docs)_files/libs/quarto-html/quarto-syntax-highlighting.css" rel="stylesheet" id="quarto-text-highlighting-styles">
<script src="Tutorial of R (Docs)_files/libs/bootstrap/bootstrap.min.js"></script>
<link href="Tutorial of R (Docs)_files/libs/bootstrap/bootstrap-icons.css" rel="stylesheet">
<link href="Tutorial of R (Docs)_files/libs/bootstrap/bootstrap.min.css" rel="stylesheet" id="quarto-bootstrap" data-mode="light">
<script src="Tutorial of R (Docs)_files/libs/htmlwidgets-1.6.4/htmlwidgets.js"></script>

<script src="Tutorial of R (Docs)_files/libs/plotly-binding-4.10.4/plotly.js"></script>

<script src="Tutorial of R (Docs)_files/libs/typedarray-0.1/typedarray.min.js"></script>

<script src="Tutorial of R (Docs)_files/libs/jquery-3.5.1/jquery.min.js"></script>

<link href="Tutorial of R (Docs)_files/libs/crosstalk-1.2.1/css/crosstalk.min.css" rel="stylesheet">

<script src="Tutorial of R (Docs)_files/libs/crosstalk-1.2.1/js/crosstalk.min.js"></script>

<link href="Tutorial of R (Docs)_files/libs/plotly-htmlwidgets-css-2.11.1/plotly-htmlwidgets.css" rel="stylesheet">

<script src="Tutorial of R (Docs)_files/libs/plotly-main-2.11.1/plotly-latest.min.js"></script>


  <script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
  <script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml-full.js" type="text/javascript"></script>

<script type="text/javascript">
const typesetMath = (el) => {
  if (window.MathJax) {
    // MathJax Typeset
    window.MathJax.typeset([el]);
  } else if (window.katex) {
    // KaTeX Render
    var mathElements = el.getElementsByClassName("math");
    var macros = [];
    for (var i = 0; i < mathElements.length; i++) {
      var texText = mathElements[i].firstChild;
      if (mathElements[i].tagName == "SPAN") {
        window.katex.render(texText.data, mathElements[i], {
          displayMode: mathElements[i].classList.contains('display'),
          throwOnError: false,
          macros: macros,
          fleqn: false
        });
      }
    }
  }
}
window.Quarto = {
  typesetMath
};
</script>

</head>

<body>

<div id="quarto-content" class="page-columns page-rows-contents page-layout-article">
<div id="quarto-margin-sidebar" class="sidebar margin-sidebar">
  <nav id="TOC" role="doc-toc" class="toc-active">
    <h2 id="toc-title">Table of contents</h2>
   
  <ul>
  <li><a href="#how-to-start-r" id="toc-how-to-start-r" class="nav-link active" data-scroll-target="#how-to-start-r">How to start R</a></li>
  <li><a href="#how-to-import-data-into-r" id="toc-how-to-import-data-into-r" class="nav-link" data-scroll-target="#how-to-import-data-into-r">How to import data into R</a></li>
  <li><a href="#data-analysis" id="toc-data-analysis" class="nav-link" data-scroll-target="#data-analysis">Data Analysis</a></li>
  <li><a href="#section" id="toc-section" class="nav-link" data-scroll-target="#section"></a></li>
  <li><a href="#making-graphs" id="toc-making-graphs" class="nav-link" data-scroll-target="#making-graphs">Making graphs</a>
  <ul class="collapse">
  <li><a href="#analysis-on-the-impact-of-interest-rate-cap-policy" id="toc-analysis-on-the-impact-of-interest-rate-cap-policy" class="nav-link" data-scroll-target="#analysis-on-the-impact-of-interest-rate-cap-policy">Analysis on the impact of interest rate cap policy</a></li>
  </ul></li>
  <li><a href="#regression-analysis" id="toc-regression-analysis" class="nav-link" data-scroll-target="#regression-analysis">Regression Analysis</a>
  <ul class="collapse">
  <li><a href="#ols-estimation" id="toc-ols-estimation" class="nav-link" data-scroll-target="#ols-estimation">OLS Estimation</a></li>
  </ul></li>
  </ul>
</nav>
</div>
<main class="content" id="quarto-document-content">

<header id="title-block-header" class="quarto-title-block default">
<div class="quarto-title">
<h1 class="title">Tutorial of R (Docs)</h1>
</div>



<div class="quarto-title-meta">

    <div>
    <div class="quarto-title-meta-heading">Author</div>
    <div class="quarto-title-meta-contents">
             <p>Daiju Aiba </p>
          </div>
  </div>
    
    <div>
    <div class="quarto-title-meta-heading">Published</div>
    <div class="quarto-title-meta-contents">
      <p class="date">July 25, 2024</p>
    </div>
  </div>
  
    
  </div>
  


</header>


<section id="how-to-start-r" class="level2">
<h2 class="anchored" data-anchor-id="how-to-start-r">How to start R</h2>
<p>Before analysis, we should set the working directory. We can choose a folder from local folders of your PC. For choosing the folder, select [Session] button, and then select <strong>[Set Working Directory]</strong>. Or you can choose the folder by using <code>setwd()</code>.</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb1"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb1-1"><a href="#cb1-1" aria-hidden="true" tabindex="-1"></a><span class="fu">setwd</span>(<span class="st">"D:/OneDrive/Document/GitHub/Analysis-on-Dollarization-in-Cambodia/R Project"</span>)</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
</div>
<p>In R, we first need to install packages to perform analysis. The packages can be download and installed by using the function install.packages(). Once we install packages, we do not need to install packages every time.</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb2"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb2-1"><a href="#cb2-1" aria-hidden="true" tabindex="-1"></a><span class="fu">install.packages</span>(<span class="st">'tidyverse'</span>) <span class="co"># This package is for efficient data management and importing STATA data into R. </span></span>
<span id="cb2-2"><a href="#cb2-2" aria-hidden="true" tabindex="-1"></a><span class="fu">install.packages</span>(<span class="st">"plotly"</span>) <span class="co"># This package is for making a interactive figures. </span></span>
<span id="cb2-3"><a href="#cb2-3" aria-hidden="true" tabindex="-1"></a><span class="fu">install.packages</span>(<span class="st">"arm"</span>)  <span class="co"># This package is for visualizing the regression results in figures. </span></span>
<span id="cb2-4"><a href="#cb2-4" aria-hidden="true" tabindex="-1"></a><span class="fu">install.packages</span>(<span class="st">"render"</span>)  <span class="co"># This package is for visualizing the regression results in figures.}</span></span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
</div>
<p>Once we download and install the packages, we can call the functions in the packages by using the function, library(). We need to call libraries every time we run R codes.</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb3"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb3-1"><a href="#cb3-1" aria-hidden="true" tabindex="-1"></a><span class="fu">library</span>(plotly) </span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stderr">
<pre><code>Loading required package: ggplot2</code></pre>
</div>
<div class="cell-output cell-output-stderr">
<pre><code>
Attaching package: 'plotly'</code></pre>
</div>
<div class="cell-output cell-output-stderr">
<pre><code>The following object is masked from 'package:ggplot2':

    last_plot</code></pre>
</div>
<div class="cell-output cell-output-stderr">
<pre><code>The following object is masked from 'package:stats':

    filter</code></pre>
</div>
<div class="cell-output cell-output-stderr">
<pre><code>The following object is masked from 'package:graphics':

    layout</code></pre>
</div>
<div class="sourceCode cell-code" id="cb9"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb9-1"><a href="#cb9-1" aria-hidden="true" tabindex="-1"></a><span class="fu">library</span>(tidyverse) </span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stderr">
<pre><code>── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
✔ dplyr     1.1.4     ✔ readr     2.1.5
✔ forcats   1.0.0     ✔ stringr   1.5.1
✔ lubridate 1.9.3     ✔ tibble    3.2.1
✔ purrr     1.0.2     ✔ tidyr     1.3.1</code></pre>
</div>
<div class="cell-output cell-output-stderr">
<pre><code>── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
✖ dplyr::filter() masks plotly::filter(), stats::filter()
✖ dplyr::lag()    masks stats::lag()
ℹ Use the conflicted package (&lt;http://conflicted.r-lib.org/&gt;) to force all conflicts to become errors</code></pre>
</div>
<div class="sourceCode cell-code" id="cb12"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb12-1"><a href="#cb12-1" aria-hidden="true" tabindex="-1"></a><span class="fu">library</span>(haven)  <span class="co"># This package is included in "tidyverse". </span></span>
<span id="cb12-2"><a href="#cb12-2" aria-hidden="true" tabindex="-1"></a><span class="fu">library</span>(shiny)</span>
<span id="cb12-3"><a href="#cb12-3" aria-hidden="true" tabindex="-1"></a><span class="fu">library</span>(readxl)</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
</div>
</section>
<section id="how-to-import-data-into-r" class="level2">
<h2 class="anchored" data-anchor-id="how-to-import-data-into-r">How to import data into R</h2>
<p>For importing a dataset, there are various functions in R.</p>
<p>We can also import a dataset in STATA format by using read_dta().</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb13"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb13-1"><a href="#cb13-1" aria-hidden="true" tabindex="-1"></a>file_path <span class="ot">&lt;-</span> <span class="st">"Data/NBC_MFI.xlsx"</span></span>
<span id="cb13-2"><a href="#cb13-2" aria-hidden="true" tabindex="-1"></a>data <span class="ot">&lt;-</span> <span class="fu">read_excel</span>(file_path, <span class="at">sheet =</span> <span class="st">"Sheet1"</span>, <span class="at">range =</span> <span class="st">"A3:BY842"</span>)</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stderr">
<pre><code>New names:
• `` -&gt; `...8`
• `` -&gt; `...9`
• `` -&gt; `...10`
• `` -&gt; `...70`</code></pre>
</div>
</div>
</section>
<section id="data-analysis" class="level2">
<h2 class="anchored" data-anchor-id="data-analysis">Data Analysis</h2>
<p>Once we import the data, you may want to calculate the sample statistics of the dataset. summary() function can be used for calculating several sample statistics for the variables in the dataset.</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb15"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb15-1"><a href="#cb15-1" aria-hidden="true" tabindex="-1"></a><span class="fu">summary</span>(data[<span class="st">"m_asset1"</span>])  </span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stdout">
<pre><code>    m_asset1       
 Min.   :     504  
 1st Qu.:    9340  
 Median :   26628  
 Mean   :  310135  
 3rd Qu.:   85926  
 Max.   :19725521  
 NA's   :6         </code></pre>
</div>
</div>
<p>Or we can select variables using “$”</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb17"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb17-1"><a href="#cb17-1" aria-hidden="true" tabindex="-1"></a><span class="fu">summary</span>(data<span class="sc">$</span>m_asset1) </span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stdout">
<pre><code>    Min.  1st Qu.   Median     Mean  3rd Qu.     Max.     NA's 
     504     9340    26628   310135    85926 19725521        6 </code></pre>
</div>
</div>
<p>If we input the whole dataset, the R will return descriptive statistics for all the variables in the dataset.</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb19"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb19-1"><a href="#cb19-1" aria-hidden="true" tabindex="-1"></a><span class="fu">summary</span>(data) </span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
</div>
<p>If you want to make a summary statistics for more than one variables at once. You should type the following codes.</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb20"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb20-1"><a href="#cb20-1" aria-hidden="true" tabindex="-1"></a><span class="fu">summary</span>(data[<span class="fu">c</span>(<span class="st">'m_asset1'</span>, <span class="st">'m_asset2'</span>, <span class="st">'m_asset3'</span>, <span class="st">"m_operation1"</span>) ])</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stdout">
<pre><code>    m_asset1           m_asset2         m_asset3         m_operation1      
 Min.   :     504   Min.   :     62   Length:839         Length:839        
 1st Qu.:    9340   1st Qu.:   1049   Class :character   Class :character  
 Median :   26628   Median :   3636   Mode  :character   Mode  :character  
 Mean   :  310135   Mean   :  46354                                        
 3rd Qu.:   85926   3rd Qu.:  11034                                        
 Max.   :19725521   Max.   :2438765                                        
 NA's   :6          NA's   :5                                              </code></pre>
</div>
</div>
</section>
<section id="section" class="level2">
<h2 class="anchored" data-anchor-id="section"></h2>
<p>We can see that variables “asset1” and “asset2” are imported as “character” (or we say “string”). The calculation of statistics require the variables in the format of “numeric”. SO in this case, we have to convert the variables into “numeric” by using the following codes.</p>
<p>Then, we can see that the sample statistics of asset1 and asset 2 are shown in the result window.</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb22"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb22-1"><a href="#cb22-1" aria-hidden="true" tabindex="-1"></a>data<span class="sc">$</span>m_asset3 <span class="ot">&lt;-</span> <span class="fu">as.numeric</span>(data<span class="sc">$</span>m_asset3)  </span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stderr">
<pre><code>Warning: NAs introduced by coercion</code></pre>
</div>
<div class="sourceCode cell-code" id="cb24"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb24-1"><a href="#cb24-1" aria-hidden="true" tabindex="-1"></a>data<span class="sc">$</span>m_operation1 <span class="ot">&lt;-</span> <span class="fu">as.numeric</span>(data<span class="sc">$</span>m_operation1)  </span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stderr">
<pre><code>Warning: NAs introduced by coercion</code></pre>
</div>
<div class="sourceCode cell-code" id="cb26"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb26-1"><a href="#cb26-1" aria-hidden="true" tabindex="-1"></a><span class="fu">summary</span>(data[<span class="fu">c</span>(<span class="st">'m_asset1'</span>, <span class="st">'m_asset2'</span>, <span class="st">'m_asset3'</span>, <span class="st">"m_operation1"</span>) ])</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stdout">
<pre><code>    m_asset1           m_asset2          m_asset3         m_operation1    
 Min.   :     504   Min.   :     62   Min.   :       0   Min.   :      0  
 1st Qu.:    9340   1st Qu.:   1049   1st Qu.:    6338   1st Qu.:   1096  
 Median :   26628   Median :   3636   Median :   21502   Median :   3674  
 Mean   :  310135   Mean   :  46354   Mean   :  258201   Mean   :  41521  
 3rd Qu.:   85926   3rd Qu.:  11034   3rd Qu.:   70182   3rd Qu.:  12150  
 Max.   :19725521   Max.   :2438765   Max.   :17730347   Max.   :2371615  
 NA's   :6          NA's   :5         NA's   :8          NA's   :8        </code></pre>
</div>
</div>
<p>If you want to calculate the sample statistics for the specific sub-sample, you can specify the sub-sample by setting conditions as follow.</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb28"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb28-1"><a href="#cb28-1" aria-hidden="true" tabindex="-1"></a>M <span class="ot">&lt;-</span> data<span class="sc">$</span>m_asset1[data<span class="sc">$</span>m_asset2 <span class="sc">&gt;</span><span class="dv">12000</span>]  </span>
<span id="cb28-2"><a href="#cb28-2" aria-hidden="true" tabindex="-1"></a><span class="fu">summary</span>(M)</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stdout">
<pre><code>    Min.  1st Qu.   Median     Mean  3rd Qu.     Max.     NA's 
   12632   109755   260771  1195924   877337 19725521        5 </code></pre>
</div>
</div>
<p>We can also see the correlation between variables as follow. (Some variables include “NA” in values. In this case, we need to write the option “<code>use</code>” )</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb30"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb30-1"><a href="#cb30-1" aria-hidden="true" tabindex="-1"></a><span class="fu">cor</span>(data[<span class="fu">c</span>(<span class="st">'m_asset1'</span>, <span class="st">'m_asset2'</span>, <span class="st">'m_asset3'</span>, <span class="st">"m_operation1"</span>) ], <span class="at">use =</span> <span class="st">"complete.obs"</span>)</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stdout">
<pre><code>              m_asset1  m_asset2  m_asset3 m_operation1
m_asset1     1.0000000 0.9647632 0.9988622    0.9940217
m_asset2     0.9647632 1.0000000 0.9513290    0.9566454
m_asset3     0.9988622 0.9513290 1.0000000    0.9931728
m_operation1 0.9940217 0.9566454 0.9931728    1.0000000</code></pre>
</div>
</div>
</section>
<section id="making-graphs" class="level2">
<h2 class="anchored" data-anchor-id="making-graphs">Making graphs</h2>
<p>The next step of the analysis is visualizing the data. We can use the package of “ggplot2” to make professional graphs.</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb32"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb32-1"><a href="#cb32-1" aria-hidden="true" tabindex="-1"></a><span class="fu">ggplot</span>(data, <span class="fu">aes</span>(<span class="at">x =</span> <span class="fu">log</span>(m_asset1), <span class="at">y=</span> <span class="fu">log</span>(staff))) <span class="sc">+</span> <span class="fu">geom_point</span>()</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stderr">
<pre><code>Warning: Removed 9 rows containing missing values or values outside the scale range
(`geom_point()`).</code></pre>
</div>
<div class="cell-output-display">
<div>
<figure class="figure">
<p><img src="Tutorial-of-R--Docs-_files/figure-html/unnamed-chunk-12-1.png" class="img-fluid figure-img" width="672"></p>
</figure>
</div>
</div>
</div>
<p>For making advanced figures, the “Plotly” package gives you a various functions for making <strong>interactive graphics</strong>.<br>
For example, here are the codes for the interactive graph.</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb34"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb34-1"><a href="#cb34-1" aria-hidden="true" tabindex="-1"></a>fig <span class="ot">&lt;-</span> <span class="fu">plot_ly</span>(data, <span class="at">x =</span> <span class="sc">~</span><span class="fu">log</span>(m_asset1), <span class="at">y =</span> <span class="sc">~</span><span class="fu">log</span>(staff), <span class="at">type =</span> <span class="st">"scatter"</span>) </span>
<span id="cb34-2"><a href="#cb34-2" aria-hidden="true" tabindex="-1"></a>fig</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stderr">
<pre><code>No scatter mode specifed:
  Setting the mode to markers
  Read more about this attribute -&gt; https://plotly.com/r/reference/#scatter-mode</code></pre>
</div>
<div class="cell-output cell-output-stderr">
<pre><code>Warning: Ignoring 9 observations</code></pre>
</div>
<div class="cell-output-display">
<div class="plotly html-widget html-fill-item" id="htmlwidget-d684df27a77fbd12c2d7" style="width:100%;height:464px;"></div>
<script type="application/json" data-for="htmlwidget-d684df27a77fbd12c2d7">{"x":{"visdat":{"8b9c20fb6cd2":["function () ","plotlyVisDat"]},"cur_data":"8b9c20fb6cd2","attrs":{"8b9c20fb6cd2":{"x":{},"y":{},"alpha_stroke":1,"sizes":[10,100],"spans":[1,20],"type":"scatter"}},"layout":{"margin":{"b":40,"l":60,"t":25,"r":10},"xaxis":{"domain":[0,1],"automargin":true,"title":"log(m_asset1)"},"yaxis":{"domain":[0,1],"automargin":true,"title":"log(staff)"},"hovermode":"closest","showlegend":false},"source":"A","config":{"modeBarButtonsToAdd":["hoverclosest","hovercompare"],"showSendToCloud":false},"data":[{"x":[11.43375237906605,10.138757283648179,10.190131586412237,10.026943356463047,11.576003545182923,10.233905786321381,8.2882830452076899,10.895979777903859,8.4937198352305945,8.2779202581721432,9.0670472021497073,7.9693577420163457,7.352441100243583,8.9743648418465956,10.348750130518358,6.4002574453088208,11.940021593204687,10.806044404955641,11.091178524287781,10.686429732212288,11.905420153010001,10.90063911886528,8.279189777195004,11.470101467779299,8.9445502459404995,8.8232062205527413,8.3864009011662137,9.3805049984995055,8.210396255104774,7.0343879299155034,9.6440041344430263,11.044153077435237,6.2225762680713688,12.565546169787345,11.696046701934748,11.898425932658796,11.338798242724431,12.419517314375421,12.037577067869556,11.451145801349762,8.4437619133303539,9.9443895438565537,9.2996324794549441,6.7274317248508551,8.4819804356604926,7.9554250889126719,9.715409458629793,8.824383730256061,10.324727579759655,11.647744777869265,6.828712071641684,12.604177399232046,11.969261111450544,11.847445797866197,11.535322762412267,12.595713203291366,12.107593951281467,11.615833976922502,8.7436911105430202,9.380167531188448,7.0664669701369576,9.0350341500761324,8.0833286087863758,8.7473520776243525,9.8944468078839787,8.936561204693394,10.128110009729737,10.377918865109015,11.674125525142072,6.7286286130847017,6.522092798170152,12.782638255884978,12.089078048973979,12.170885785440792,11.899764852955196,13.028650321518336,12.508019983525998,11.909497816130081,8.2358907259284955,10.007171663813009,8.6996814009895136,7.1808311990445555,9.3027372212421504,7.203405521083095,9.0661235212157738,9.1420615312228879,9.4454124941556667,10.020914969412093,9.0917820358520469,10.180475142322448,8.6499743026500564,10.429044140902112,11.759011806144656,7.2406496942554659,13.085925508545536,12.529369176794221,12.766919104450741,12.200341252430126,13.351910382775023,12.985844670052149,12.09340214357298,6.7080840838530698,8.3454554281619284,8.479698986988657,10.784979778867587,9.0009764440703446,7.8597991805621099,9.7760518292264447,9.3375015175928624,7.5390270558239951,9.0452298519125822,9.6379582847254799,9.9349862195954994,10.019758334201514,9.1997848580366668,9.429315246418172,9.321792297270326,8.1972633714143353,10.398427667071894,9.2857260988820727,10.474212829509952,8.2679623053387097,12.131203614613918,7.1268908088988079,13.468217183447473,12.725244343720812,13.106319357684647,12.471397906532847,13.819786403493728,13.301638632261877,12.30652413159482,7.8054746252708567,9.2999068153352251,8.2579041934656736,7.9146177090406793,7.4330753488985799,11.33624795056136,9.1191018915419111,9.297618380083243,10.122502593266558,8.2807110756628468,9.3716936223339413,7.6299757070277892,8.9654623285159669,10.1251099474784,10.092577816525454,10.16419660173648,6.4551985633401223,9.1671196695216199,9.8638627577528606,9.8390556923767392,9.5392123712528267,8.7189905247108488,10.579514006287654,9.5385643997408991,10.266566944147854,9.5887768076964282,12.416280895395888,8.2837467471061306,13.818572864314275,12.914184790348802,13.483708001396225,12.766508097449274,14.406903490238257,13.632670066547036,12.584283028305117,11.268532740616845,10.930156191879892,8.2114829164450658,8.0602242404409576,7.7993433982159202,9.3629756183997763,9.7537106272179006,10.34309640521113,8.9879465395525191,9.7799064907647733,7.3664451483275988,8.9536400371331304,10.675376595036562,10.326661594425065,10.391269703133506,7.7007477945117984,9.1903417254694926,10.957241935562411,10.098889848868613,9.5501641288309091,8.970177815492379,8.6238928100752936,9.4178422273004347,10.643112702392486,9.8310243808024129,10.046808371980351,10.204443634218446,12.847123577842435,8.3499572720403243,14.157460976196283,13.093306691081485,14.069641793094974,13.113111672055522,14.866936790193931,14.205886122726769,12.975050344166542,11.310986376548835,11.588124584463255,8.1858239125309264,8.7834314806118066,9.250514476661138,9.9368749387180504,10.603751349800746,9.4529719913140688,9.5761765236110996,9.8362574122395685,7.4257451779321455,9.0347552742062653,11.288161226051065,10.476483990382269,10.55400981219703,8.7769648672590819,9.1047131540898114,11.810390354245486,10.564603930477686,9.9538849957688331,9.0122613153151505,9.7222366224168475,10.953257890693916,10.04775969993265,8.8206122848344055,10.894349249366295,10.133530845790995,9.9821138729913184,10.246356074951173,8.3689692238813418,13.213606607459321,9.2614243794647582,14.477717384379183,13.377166776586035,14.407151341754881,13.31187715803809,13.71119896976742,15.260423200132577,14.596475007362431,13.288382637590521,11.36123813194474,11.837340230133128,8.1446385440153115,8.2098328727326315,8.4378360819998299,9.1902029686487605,9.4166437196809358,10.189132175797232,7.9571142962632191,7.3562990334553762,10.791790453546769,9.998686817098676,10.474393367590205,9.8622842353216154,7.4747381489202693,8.9923945390892719,11.463222799598178,10.492867946776704,10.830526118955007,9.8372980693103376,8.870625082338675,9.1493486202758181,11.979923582186135,10.456775936030651,9.2460626650957138,10.741904090477016,11.383186870584401,11.572960077471276,12.388616635917275,10.341677029712329,9.332993308172215,9.0047239688612777,9.0329824758111066,8.6969681751102659,9.557725700741063,11.031283006560038,8.7975847525565563,10.449208104416009,9.7337645002545479,10.414286075934907,9.9362799560009503,8.4246755189314388,10.600256665971029,11.201220608875902,9.7634968865057079,14.783629615071447,13.6662667580202,14.677753003944433,13.471028195773748,13.837238193986778,15.434535190598746,13.418789553509669,11.624991836036598,8.1966628055420347,8.4540695621802033,8.4808465840611245,10.10361382710084,9.0424470261409535,9.3384952118095885,10.522531684007156,9.5228739224473351,8.3854798023641628,10.358733445098501,8.4720347246433487,7.223791544930446,10.775078154635231,8.755048787912969,10.515333838403771,9.0089009477844666,10.813006004200195,9.9122064323953616,7.558104555865091,11.607392016292822,10.824783497406971,10.32568394219625,8.9759321113918205,10.677897388638206,7.5533967201458756,10.748098807228001,10.90904569796791,6.4662691332947588,8.7683110670486037,9.1206607110082683,8.3704227769748254,8.4973802040663919,12.167425731722556,10.72856412445152,9.493042565387567,11.301781875253546,9.2592879523264671,11.484379477658443,11.226250218832021,12.662468767410191,9.6499658471533234,10.502568803890822,10.949542941786467,9.6871401053022659,9.919688603897697,9.5187584595116128,9.0960119871360767,8.4325390340002855,8.9802716469034305,9.7522355009573314,11.113091422610241,9.009915901753665,10.757948198814249,9.8307964223414785,10.903481729554507,10.084299637316878,9.4485770468900263,8.8067198116433207,10.594686837178036,11.540643739527905,10.193719608514645,14.988158997159376,13.95732187719228,14.842327802724917,13.70269414942112,14.223567770332249,15.772750919909509,13.586729156296558,11.897467810665047,9.3515318138690056,7.7777103858394518,7.9909400396342756,10.846654170460297,9.730653843428863,9.2804546944018984,9.5747813818091707,10.497206392796993,9.8691588579237521,9.1748447297233238,10.400267323536607,7.7653204072628146,8.6297601581178416,10.811662641487457,9.5989115783413759,10.6779041649588,8.970905293981648,11.017801226756736,9.9139132654268529,7.9725723551479408,11.415987689350144,11.770850274238395,10.792442626550981,8.9557006065995939,8.4245288702388468,10.921337082689638,10.657115062149867,6.3817373848730172,8.7070900000688169,9.1913980944729587,8.8162440881834687,9.6070923642316348,8.9385465567060489,12.303955694484438,11.130526916437184,9.4462703869299709,9.4927153868771104,11.866377651400171,9.8009525967770497,10.57914225285421,10.821188729265128,8.9606558418322155,12.523662694691891,7.51847056252734,9.8300047772138246,10.874381614580077,11.599675932926056,9.7187192849850792,9.9343301420205652,9.2962235294321012,10.201462657013312,7.9033561425692644,8.8681035520251168,10.040433839017822,11.159931537768838,9.2184444450884779,10.996501332090498,9.8631971875092006,11.096388893774952,10.165398445015299,9.601936819928989,8.7474872448472887,11.28156251425129,10.38335190465996,10.43143727837384,11.447731326295774,12.143527655987397,10.558512995847497,15.175650607482105,14.169622720783002,15.123009516535404,13.874174671003367,14.719411249312408,16.071203185020043,13.780891162493479,12.290105842139864,9.583420019940192,9.8620924771697425,7.9061788403948148,10.576942099750337,9.4330838432690527,9.8673939448878887,9.5104449644265205,10.996785746380469,10.053587180780166,10.245160527556513,10.745765692323122,8.5356223268846048,7.1546153569136628,11.120889777173725,11.082357910301223,10.661743404167277,8.928375259853631,11.102261868103218,9.8804747782270557,8.5976665755661141,8.5650305208303976,11.407464944312069,12.183699216553281,10.955602047544657,9.2970683754860062,8.8232062205527413,11.258523417753246,10.347852809601848,11.237606651501846,8.6011666251924161,9.1264151370384212,9.6266135288009398,10.107855948524003,9.531191227694439,12.746275501656838,11.324171263005734,10.005141206262628,12.211647079462775,10.23988835803477,10.407197922816518,11.283587769492691,10.545762402722318,8.8866856390655844,11.762991336350483,8.656259239539235,9.8310781370179878,11.055798573538173,8.7406566915413677,8.716207971151853,9.763535592108683,9.9920934908701522,9.4903934172634727,10.269518591398885,7.9830989407108923,8.8428933310555387,10.175345074640937,9.1929907336410697,11.516050576717726,9.8304866596516369,10.353607301184724,11.052935530906733,7.9124231214737053,9.881599752778099,8.7818624895589448,11.879732901387515,8.710124927322207,10.464473829493734,10.375302041185826,11.918777165008768,12.705792831563842,10.574670270717423,10.248777937608223,15.366821352221729,14.362076421981598,15.419272190761674,14.023591637672114,15.240608958902707,16.353493569862657,14.244765757692116,12.825118392376559,9.7300266241743696,9.9709592676511409,8.0762045272390264,10.447931687925744,9.4852411100632299,10.351948291105389,9.4818930624980808,10.334522936755823,10.659233874852593,11.020348974872102,8.5101685764792734,11.662060731469461,11.56495798606238,11.49758845195999,10.688689620179726,8.858084222199162,11.15797760019988,9.8750880780144303,8.3689251747471349,8.7305288017393607,11.663627347383722,12.4059844167185,11.011753098232376,9.7555674224595066,9.2986259368435427,10.36992232096731,10.462503160399518,8.5391503587682802,9.1155900354303725,10.469851945892822,10.403717237088715,9.8243361142306913,13.326581772332133,11.49146686731166,10.248317622106937,12.581356857936775,9.9948353469954032,10.373803632963909,11.752587826377331,10.205109511721595,8.8311276350120842,10.913851335650172,8.6520736736100563,9.9160088330897995,8.9452022639592972,9.9439574850898413,9.9439574850898413,10.313708002728152,9.5600813313119861,9.9529441612487197,8.8853025129806333,8.8324417915858238,10.544551653225849,9.4946166512931303,11.74286189237203,9.8596401527558513,11.149369759939274,10.501169541278006,9.1270674527823612,12.000541825439107,8.703008637464448,10.501939364256749,10.38514179900184,12.210741728378435,13.102397376763451,10.689099960768168,11.128380007114567,14.453915873066055,15.541228332410677,15.29547102085983,12.710999908114795,16.503219946974845,14.955338683586525,13.165192955379684,9.6663718436550354,10.091708341261072,8.160803920954665,8.5028914067053769,9.5009182475399889,10.485451744135313,9.8526152221623722,9.3521870962044193,12.066339202748898,10.229151590440738,10.556333436322548,10.797880263309066,10.924012165653831,8.3437917319968413,12.230638420808742,12.02650928142314,11.814273728185825,10.651809235840728,11.873253727406864,11.143281065776831,9.8656299099798872,8.7767843837014929,8.628734566149145,11.571232108231282,12.439309091792234,11.008346953964704,8.9343233310549053,9.7477105509642854,9.2136349389256136,11.723696795020878,10.405353154930607,10.503449793368381,8.482601746646619,9.0973956129600477,11.083864143006878,10.145609862448119,8.7408166275672983,9.4919792208806779,11.521746445476007,10.265975567789152,10.164889815967427,10.121296902259635,12.459935490503751,10.266497388607728,9.2466723012235725,10.867768128408946,8.62191350218664,9.9139822896287697,11.071034933244212,8.581294116822761,9.0264175338152537,8.8528079176233216,9.9824835587626257,11.012710020316254,9.3954081544381634,10.096130658401954,8.9374812284160399,8.7794035978943494,10.721437517010912,9.5337997358034841,11.707562540153498,9.8205949544465625,10.463646050320772,9.3538344716149115,11.06291268060075,11.515272708038577,8.6294498737619048,12.030611502192858,10.46495876097101,10.363188288785967,12.225836056371124,10.727860344448946,14.709884870056193,15.671088132642824,15.420438716728544,13.115876382274386,16.683400028145719,13.503508470165814,9.9864490732504745,7.6123368371677458,9.5247130596810088,10.809970343419197,9.8884754324156248,9.4311612279207466,12.644195309649945,10.2185902205639,11.467833952348418,10.573596376469498,11.125555645131156,8.2311098403281537,12.936493934298303,12.015142137830576,12.109952637903797,10.57234204052703,12.307518508925403,10.796243501276619,9.8507194869974715,8.6695708718371201,9.5092590763539508,11.826830685462287,12.642477478989177,11.016988453697989,8.8677092080393862,9.9745981799940804,9.1552504056582222,11.63195217139187,10.417029483796346,10.686978052993675,8.4098306730877379,9.0410929746694997,11.318612295323895,9.612533466213927,8.791486026749002,9.1048687390339484,8.4819804356604926,11.589960577437083,10.37477161168151,9.6276022899638587,10.565969318785188,10.178160370394268,12.51210776573342,10.268234827365733,9.2162230351343375,10.159253170667593,9.9342592112028818,10.98136978397784,8.5426659873892685,8.8913740094846361,8.6877794919917708,10.148510005568779,10.898330651308273,9.2274924307937489,10.32094710549266,9.7411450780574853,8.7876782390394972,10.827845655488042,9.5187804975124735,11.604610901504739,9.7506859622781654,10.283874140267756,9.3612572572930439,10.932749763069445,11.903391987871199,8.165932137321585,11.964663285409072,10.543655808305187,10.495183233934963,12.465613697712399,10.75479166289073,14.90702773575646,15.931337426694355,15.633024514818185,13.396832542583809,16.797423837528633,13.963356260271219,9.8342982331831301,10.009962447043133,7.2548848100773382,9.5639506245420698,11.355007698573726,9.8285484658716342,9.1196495066916796,12.871547967450207,10.197536811366069,12.171015253714771,10.5368847286903,11.535674727063007,8.0487882835341988,13.415662643840687,12.127354060818769,12.328086717714372,10.628787256112481,10.304911171484573,9.0438134210808698,10.862416229094517,9.7032056703651808,8.6621589616664227,8.6242522637096446,9.8855272271591357,12.193630562840269,12.751801019605185,11.032952304687003,9.305741456739435,10.113505336631411,8.9655900669079145,11.584138536654374,10.358885029392502,12.194986419792608,10.707885367893804,8.2947993589925737,9.0112794911779304,11.280425781231992,9.4807491157575061,8.7326270996603945,9.366317953430535,10.075379913839543,10.252911269760668,11.879559650613515,10.077314801294376,9.8441090290166287,10.696525315910868,10.186257580626888,12.899799657955128,10.289192032466138,9.18296917518005,9.2785596109533266,10.004418271114568,11.131225710412325,8.5756507609878057,8.9910643321884613,8.7632717140129426,10.189718572720594,10.862550376254152,9.326433090963036,10.588148829445775,9.8254719555513894,8.6881167032578226,10.910459585649052,9.5139942139376625,11.518987056348823,9.4439885559354781,9.7371968128147017,10.326301298978905,8.5295169411050686,9.4314017570860678,8.7417757069247006,10.901892690787205,11.642979568827707,8.9488457292780499,12.251848748166758,10.70699025292366,10.538661281320572,9.1942109900462992,12.457484846808923,10.763969547581704,10.232611427387569],"y":[5.9889614168898637,4.4773368144782069,5.1298987149230735,4.9199809258281251,6.4134589571673573,5.4293456289544411,3.9318256327243257,5.6347896031692493,3.8501476017100584,2.0794415416798357,3.4965075614664802,1.0986122886681098,1.9459101490553132,4.3944491546724391,5.4249500174814029,2.7080502011022101,6.4150969591715956,5.8493247799468593,5.3518581334760666,5.4071717714601188,6.5820251388928259,5.7990926544605257,4.0775374439057197,6.1420374055873559,4.219507705176107,2.7725887222397811,2.0794415416798357,3.5263605246161616,3.1780538303479458,1.9459101490553132,4.6913478822291435,5.5721540321777647,2.6390573296152584,6.6437897331476723,6.3368257311464413,6.0753460310886842,5.9661467391236922,6.9314718055994531,6.481577129276431,6.2557500417533669,3.9889840465642745,4.7184988712950942,2.7725887222397811,1.791759469228055,2.0794415416798357,2.8332133440562162,4.0430512678345503,3.8712010109078911,4.9272536851572051,5.7745515455444085,2.6390573296152584,6.8710912946105456,6.6411821697405911,6.2344107257183712,6.261491684321042,3.912023005428146,4.8751973232011512,5.9080829381689313,4.2046926193909657,1.791759469228055,2.0794415416798357,2.0794415416798357,1.0986122886681098,1.0986122886681098,2.6390573296152584,4.1108738641733114,2.6390573296152584,7.1276936993473985,6.6160651851328174,5.1357984370502621,2.7080502011022101,7.167809184316444,6.7381524945959574,6.654152520183219,6.3733197895770122,7.2723983925700466,6.8721281013389861,6.4409465406329209,2.8332133440562162,2.9957322735539909,4.1588830833596715,2.6390573296152584,2.8903717578961645,1.9459101490553132,2.0794415416798357,2.3978952727983707,3.7376696182833684,4.3174881135363101,4.0073331852324712,4.9487598903781684,3.6888794541139363,5.2311086168545868,6.1246833908942051,3.1780538303479458,7.4342573821331355,6.8803840821860049,6.9994224675079613,6.5750758405996201,7.3138868316334618,7.1996783456911722,6.5510803350434044,1.9459101490553132,3.2958368660043291,3.1780538303479458,3.8918202981106265,4.219507705176107,2.8332133440562162,5.0937502008067623,2.8903717578961645,2.0794415416798357,2.0794415416798357,2.6390573296152584,4.2046926193909657,4.5325994931532563,3.2580965380214821,3.784189633918261,4.1743872698956368,3.2580965380214821,4.9836066217083363,3.6888794541139363,5.3327187932653688,3.5263605246161616,6.300785794663244,3.3672958299864741,7.7935868033715838,7.0791843946096682,7.15305163493748,6.7428806357919031,7.6662219256627253,7.4442486494967053,6.7093043402582984,2.5649493574615367,4.3040650932041702,2.5649493574615367,2.6390573296152584,2.3978952727983707,4.4308167988433134,4.3438054218536841,3.4011973816621555,5.3612921657094255,2.4849066497880004,2.8903717578961645,2.0794415416798357,2.0794415416798357,3.3322045101752038,4.4543472962535073,4.5217885770490405,3.1780538303479458,3.7376696182833684,3.5835189384561099,4.0073331852324712,4.3174881135363101,3.5263605246161616,5.0875963352323836,3.6635616461296463,5.3033049080590757,3.6109179126442243,6.543911845564792,3.5263605246161616,7.2751723194527713,7.9762519437456234,7.3864708488298945,6.9017372066565743,7.9247959139564355,7.6718267978787811,6.8741984954532942,4.6634390941120669,5.2470240721604862,2.4849066497880004,3.0910424533583161,2.4849066497880004,4.4067192472642533,3.4657359027997265,5.8081424899804439,2.5649493574615367,2.8903717578961645,2.1972245773362196,2.0794415416798357,3.5553480614894135,4.6249728132842707,4.6151205168412597,3.1354942159291497,3.1780538303479458,5.1357984370502621,4.3694478524670215,4.3820266346738812,2.7725887222397811,2.7725887222397811,3.9318256327243257,5.2626901889048856,4.1431347263915326,5.2522734280466299,4.219507705176107,6.7730803756555353,3.713572066704308,7.9724660159745655,7.461640392208575,7.5553819442402732,7.1428274011616208,8.3187422526923989,7.8115684893451798,7.0825485693552999,5.0039463059454592,5.8051349689164882,2.4849066497880004,3.7376696182833684,3.2958368660043291,3.5553480614894135,5.6594822157596214,2.8903717578961645,4.6913478822291435,2.9957322735539909,2.1972245773362196,2.0794415416798357,3.8286413964890951,4.6347289882296359,4.5951198501345898,2.8332133440562162,3.1780538303479458,5.7268477475871968,4.5432947822700038,4.5108595065168497,3.1780538303479458,5.6167710976665717,3.5835189384561099,4.219507705176107,2.3025850929940459,5.3471075307174685,4.1108738641733114,5.1532915944977793,4.290459441148391,3.6375861597263857,7.0527210492323231,4.1108738641733114,8.1487348089371689,7.6619975589018932,7.715569534520208,7.4109518755836366,7.3118861640771646,8.5726278983043382,8.0465493572830784,7.2584121505953068,5.2729995585637468,6.061456918928017,2.4849066497880004,2.7725887222397811,2.9444389791664403,3.970291913552122,4.1588830833596715,3.9889840465642745,2.6390573296152584,1.6094379124341003,5.8171111599632042,3.5835189384561099,5.3181199938442161,2.9444389791664403,2.3025850929940459,2.0794415416798357,4.3694478524670215,4.7004803657924166,4.9052747784384296,3.2580965380214821,2.9957322735539909,2.3978952727983707,6.0063531596017325,4.6821312271242199,3.3672958299864741,6.3595738686723777,6.9985096422506015,3.7612001156935624,4.5217885770490405,4.3694478524670215,4.0253516907351496,3.3672958299864741,2.3025850929940459,4.9558270576012609,4.5432947822700038,5.472270673671475,2.0794415416798357,4.1431347263915326,4.8978397999509111,4.3944491546724391,2.6390573296152584,4.0253516907351496,2.1972245773362196,5.0689042022202315,4.4067192472642533,8.3209349688834102,7.7617449846589128,7.7514753180214564,7.4265490723973047,7.5352967024440884,8.7261566791566132,7.3058600326840093,5.3327187932653688,3.044522437723423,4.1271343850450917,3.5263605246161616,1.791759469228055,4.3820266346738812,4.1743872698956368,4.1431347263915326,4.1431347263915326,2.9957322735539909,4.3694478524670215,2.9444389791664403,1.3862943611198906,5.7868973813667077,3.1780538303479458,4.3307333402863311,3.044522437723423,5.3981627015177525,2.9444389791664403,2.3025850929940459,4.6634390941120669,6.5971457018866513,4.499809670330265,3.7612001156935624,4.6443908991413725,2.4849066497880004,3.0910424533583161,4.962844630259907,1.791759469228055,3.1780538303479458,2.7080502011022101,3.1354942159291497,2.7080502011022101,5.916202062607435,4.8520302639196169,3.7612001156935624,6.4831073514571989,2.8903717578961645,6.9255951971104679,3.6635616461296463,4.1743872698956368,3.6635616461296463,4.3944491546724391,4.6913478822291435,3.5263605246161616,2.1972245773362196,2.9444389791664403,2.8903717578961645,4.4308167988433134,2.4849066497880004,4.7621739347977563,5.5134287461649825,2.3025850929940459,4.4426512564903167,4.8121843553724171,4.4188406077965983,3.4657359027997265,2.6390573296152584,4.5108595065168497,2.3025850929940459,5.1416635565026603,4.6051701859880918,8.2887858104269281,7.8216431262399819,8.0143357372994242,7.4157769754153939,7.6328855053951328,8.8619170042352149,7.2363393427543441,5.8435444170313602,3.4339872044851463,3.8066624897703196,3.0910424533583161,1.9459101490553132,3.7612001156935624,3.8066624897703196,4.3040650932041702,4.7184988712950942,4.1431347263915326,3.2580965380214821,4.5432947822700038,2.6390573296152584,1.3862943611198906,5.3327187932653688,4.3567088266895917,4.6051701859880918,2.8332133440562162,5.4595855141441589,2.9444389791664403,2.4849066497880004,4.8598124043616719,6.4583382833447898,4.4426512564903167,4.1743872698956368,2.7080502011022101,3.4011973816621555,4.7706846244656651,1.6094379124341003,2.9957322735539909,2.0794415416798357,2.8903717578961645,3.5263605246161616,3.7612001156935624,5.9532433342877846,5.0814043649844631,3.044522437723423,3.8501476017100584,6.5985090286145152,2.7080502011022101,5.4553211153577017,4.1896547420264252,2.0794415416798357,3.4339872044851463,1.3862943611198906,4.1896547420264252,4.6913478822291435,5.0751738152338266,3.5263605246161616,2.3025850929940459,2.9444389791664403,3.5263605246161616,4.0775374439057197,2.4849066497880004,4.8828019225863706,5.4680601411351315,2.5649493574615367,4.8751973232011512,4.8828019225863706,4.3944491546724391,4.2046926193909657,3.044522437723423,3.8712010109078911,3.3672958299864741,4.3438054218536841,4.9052747784384296,5.0238805208462765,5.5490760848952201,4.6913478822291435,8.3187422526923989,7.941295570906532,8.1107275829744889,7.4312996751559028,7.7523351633022921,8.9359035262744229,7.2647301779298674,5.9480349891806457,3.8918202981106265,3.5263605246161616,2.8903717578961645,2.7080502011022101,4.0604430105464191,3.6888794541139363,3.784189633918261,5.1761497325738288,4.0430512678345503,3.2188758248682006,4.5432947822700038,2.6390573296152584,2.4849066497880004,5.3278761687895813,4.9272536851572051,4.4659081186545837,2.5649493574615367,4.3944491546724391,2.8903717578961645,2.0794415416798357,2.9444389791664403,4.7791234931115296,6.481577129276431,4.3944491546724391,4.3307333402863311,2.7080502011022101,3.5263605246161616,4.5108595065168497,3.6888794541139363,1.6094379124341003,1.3862943611198906,2.8903717578961645,3.8066624897703196,3.3322045101752038,6.1590953884919326,5.1532915944977793,3.3672958299864741,6.6933236682699491,2.7725887222397811,5.393627546352362,5.4847969334906548,0.69314718055994529,2.1972245773362196,3.044522437723423,1.3862943611198906,4.1271343850450917,4.7449321283632502,3.6375861597263857,2.1972245773362196,3.6375861597263857,2.3025850929940459,3.1354942159291497,3.5263605246161616,4.3040650932041702,2.6390573296152584,4.6913478822291435,2.8332133440562162,5.2983173665480363,4.9052747784384296,4.2626798770413155,4.4659081186545837,3.044522437723423,4.1896547420264252,3.4965075614664802,3.6109179126442243,0.69314718055994529,4.4773368144782069,4.8978397999509111,5.0875963352323836,5.7960577507653719,4.5951198501345898,4.5643481914678361,8.4335941675399244,8.0362499421321161,8.3852605201554127,7.4938738867835593,7.9218984110237969,9.1150401921218585,7.4277388405328937,6.2672005485413624,3.9318256327243257,3.8918202981106265,2.8903717578961645,2.9444389791664403,4.0943445622221004,4.1743872698956368,3.5835189384561099,3.9512437185814275,3.0910424533583161,4.6347289882296359,2.3978952727983707,4.1431347263915326,5.4930614433405482,5.2094861528414214,4.3944491546724391,2.0794415416798357,5.6347896031692493,2.7725887222397811,3.044522437723423,2.9957322735539909,4.8598124043616719,6.4567696555721632,4.3040650932041702,4.499809670330265,2.8332133440562162,4.3567088266895917,3.5835189384561099,1.791759469228055,1.6094379124341003,3.2958368660043291,3.9318256327243257,3.1780538303479458,6.3919171133926023,5.1416635565026603,3.4339872044851463,6.9057532763114642,2.4849066497880004,5.3082676974012051,5.5174528964647074,1.791759469228055,2.1972245773362196,3.044522437723423,1.3862943611198906,3.9889840465642745,3.8918202981106265,2.3978952727983707,3.8286413964890951,2.3978952727983707,3.4657359027997265,3.5835189384561099,4.3040650932041702,2.7080502011022101,4.4886363697321396,3.4965075614664802,5.3375380797013179,4.5432947822700038,4.6249728132842707,2.9444389791664403,4.0253516907351496,3.5263605246161616,1.9459101490553132,4.5108595065168497,4.9272536851572051,5.2364419628299492,5.8021183753770629,4.5432947822700038,4.290459441148391,8.0633778223670269,8.421122722665503,8.0519780789022999,7.108244139731541,9.1096356678545511,8.0010199613236512,6.4019171967271857,4.0775374439057197,3.8286413964890951,2.8903717578961645,1.9459101490553132,3.9889840465642745,4.5849674786705723,3.4965075614664802,3.970291913552122,5.5012582105447274,4.0430512678345503,4.1743872698956368,2.9444389791664403,4.7874917427820458,2.3978952727983707,4.8751973232011512,5.8141305318250662,5.5134287461649825,4.5747109785033828,4.2766661190160553,5.5294290875114234,2.8332133440562162,2.9957322735539909,3.2188758248682006,4.7621739347977563,6.300785794663244,4.3438054218536841,2.7725887222397811,4.4659081186545837,2.9957322735539909,3.6109179126442243,4.3307333402863311,3.6635616461296463,1.9459101490553132,1.9459101490553132,3.1780538303479458,3.9512437185814275,1.9459101490553132,3.4657359027997265,5.2470240721604862,3.5835189384561099,2.9444389791664403,5.3327187932653688,5.7104270173748697,2.3978952727983707,2.5649493574615367,3.044522437723423,1.9459101490553132,4.0253516907351496,4.6249728132842707,2.6390573296152584,4.0253516907351496,2.7725887222397811,4.1431347263915326,2.4849066497880004,3.3322045101752038,3.784189633918261,4.5325994931532563,2.4849066497880004,4.5432947822700038,3.5835189384561099,5.2522734280466299,4.6347289882296359,4.3820266346738812,2.3025850929940459,4.5643481914678361,3.044522437723423,4.0253516907351496,3.4657359027997265,4.5325994931532563,4.9698132995760007,5.5683445037610966,4.3438054218536841,8.1679193629578162,8.4487001949709377,8.1007682430717303,7.0698741284585722,9.1409902938413889,6.2878585601617845,3.7376696182833684,2.6390573296152584,3.8501476017100584,4.6728288344619058,3.2580965380214821,3.8918202981106265,5.8464387750577247,4.2341065045972597,4.6539603501575231,2.8903717578961645,4.8520302639196169,2.3978952727983707,5.1647859739235145,5.9107966440405271,5.5568280616995374,4.4773368144782069,4.2341065045972597,5.4510384535657002,2.7725887222397811,2.9444389791664403,3.2580965380214821,4.6913478822291435,6.4183649359362116,4.4543472962535073,2.6390573296152584,4.4773368144782069,2.9957322735539909,3.6375861597263857,4.2484952420493594,3.6888794541139363,1.9459101490553132,2.1972245773362196,2.9957322735539909,3.8918202981106265,1.9459101490553132,3.044522437723423,3.1780538303479458,5.4595855141441589,3.5553480614894135,4.0430512678345503,2.9957322735539909,5.3565862746720123,5.8171111599632042,2.3978952727983707,2.6390573296152584,3.044522437723423,3.8918202981106265,4.6151205168412597,2.8332133440562162,3.7612001156935624,2.4849066497880004,4.2626798770413155,2.4849066497880004,3.3322045101752038,3.6635616461296463,4.8202815656050371,2.7080502011022101,4.4659081186545837,3.6635616461296463,4.8828019225863706,4.5747109785033828,4.3174881135363101,2.0794415416798357,4.4188406077965983,2.8332133440562162,3.4657359027997265,3.5263605246161616,4.2626798770413155,4.990432586778736,5.6903594543240601,4.2626798770413155,8.1693363959283865,8.4709398068987749,8.1704685783306736,7.2591161280971006,9.1667019149463531,6.3456363608285962,3.784189633918261,3.8066624897703196,1.3862943611198906,3.6375861597263857,5.0039463059454592,3.2580965380214821,3.713572066704308,5.9322451874480109,4.2341065045972597,5.0369526024136295,2.3978952727983707,5.1357984370502621,2.3978952727983707,5.5053315359323625,5.9661467391236922,5.5529595849216173,4.290459441148391,3.5835189384561099,2.5649493574615367,5.3278761687895813,2.7725887222397811,2.0794415416798357,2.8903717578961645,3.4657359027997265,5.2678581590633282,6.4425401664681985,4.4188406077965983,2.7080502011022101,4.5643481914678361,3.044522437723423,3.6109179126442243,4.2766661190160553,5.6167710976665717,3.8066624897703196,2.6390573296152584,2.0794415416798357,3.044522437723423,3.8286413964890951,2.1972245773362196,2.7080502011022101,3.3672958299864741,4.3040650932041702,5.7397929121792339,3.0910424533583161,4.2046926193909657,3.0910424533583161,5.3278761687895813,6.0282785202306979,2.3978952727983707,2.7080502011022101,3.044522437723423,4.0073331852324712,4.9558270576012609,3.1354942159291497,3.5553480614894135,2.6390573296152584,4.2626798770413155,2.4849066497880004,3.3322045101752038,3.6635616461296463,4.8040210447332568,2.1972245773362196,4.4886363697321396,3.7612001156935624,4.9558270576012609,0,4.4543472962535073,4.3307333402863311,2.4849066497880004,2.1972245773362196,1.9459101490553132,4.5108595065168497,2.8903717578961645,3.4965075614664802,3.5263605246161616,4.3944491546724391,4.9272536851572051,5.0875963352323836,5.7037824746562009,4.3307333402863311,4.3567088266895917],"type":"scatter","mode":"markers","marker":{"color":"rgba(31,119,180,1)","line":{"color":"rgba(31,119,180,1)"}},"error_y":{"color":"rgba(31,119,180,1)"},"error_x":{"color":"rgba(31,119,180,1)"},"line":{"color":"rgba(31,119,180,1)"},"xaxis":"x","yaxis":"y","frame":null}],"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.20000000000000001,"selected":{"opacity":1},"debounce":0},"shinyEvents":["plotly_hover","plotly_click","plotly_selected","plotly_relayout","plotly_brushed","plotly_brushing","plotly_clickannotation","plotly_doubleclick","plotly_deselect","plotly_afterplot","plotly_sunburstclick"],"base_url":"https://plot.ly"},"evals":[],"jsHooks":[]}</script>
</div>
</div>
<section id="analysis-on-the-impact-of-interest-rate-cap-policy" class="level3">
<h3 class="anchored" data-anchor-id="analysis-on-the-impact-of-interest-rate-cap-policy">Analysis on the impact of interest rate cap policy</h3>
<p>We can also create a new variable from variables in the data. For example, if you want to create average implicit interest rate from the individual bank data, we can calculate it as follow:</p>
<p><span class="math display">\[
InterestRate = \frac{InterestIncome}{Loans} *100
\]</span></p>
<p>In R, we can create new variables in data in several ways. One of the good ways to create new variables from readability of R code is using <code>mutate()</code> function from <code>dplyr</code> package.</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb37"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb37-1"><a href="#cb37-1" aria-hidden="true" tabindex="-1"></a><span class="fu">library</span>(dplyr)</span>
<span id="cb37-2"><a href="#cb37-2" aria-hidden="true" tabindex="-1"></a>data <span class="ot">&lt;-</span> data <span class="sc">|&gt;</span></span>
<span id="cb37-3"><a href="#cb37-3" aria-hidden="true" tabindex="-1"></a>    <span class="fu">mutate</span>(<span class="at">interest_rate =</span> m_operation1<span class="sc">/</span>m_asset3<span class="sc">*</span><span class="dv">100</span>)</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
</div>
<p>Or we can also create the new variable as follow:</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb38"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb38-1"><a href="#cb38-1" aria-hidden="true" tabindex="-1"></a>data[<span class="st">"interest_rate"</span>] <span class="ot">&lt;-</span> data[<span class="st">"m_operation1"</span>]<span class="sc">/</span>data[<span class="st">"m_asset3"</span>]<span class="sc">*</span><span class="dv">100</span></span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
</div>
<p>Let’s see the created variable.</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb39"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb39-1"><a href="#cb39-1" aria-hidden="true" tabindex="-1"></a><span class="fu">summary</span>(data[<span class="st">"interest_rate"</span>])</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stdout">
<pre><code> interest_rate    
 Min.   : 0.7526  
 1st Qu.:13.5661  
 Median :17.2740  
 Mean   :    Inf  
 3rd Qu.:23.5880  
 Max.   :    Inf  
 NA's   :10       </code></pre>
</div>
</div>
<p>There is “Inf” value. This means some observations have “0” in loans and the calculation of division produced infinite values. In this case, the calculation of statistics produce the meaningless results as “Inf”. We can modify it by using following code. We can see that the abovementioned problems were solved</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb41"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb41-1"><a href="#cb41-1" aria-hidden="true" tabindex="-1"></a>data<span class="sc">$</span>interest_rate[<span class="fu">is.infinite</span>(data<span class="sc">$</span>interest_rate)] <span class="ot">&lt;-</span> <span class="cn">NA</span></span>
<span id="cb41-2"><a href="#cb41-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb41-3"><a href="#cb41-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb41-4"><a href="#cb41-4" aria-hidden="true" tabindex="-1"></a><span class="fu">summary</span>(data[<span class="st">"interest_rate"</span>])</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stdout">
<pre><code> interest_rate      
 Min.   :   0.7526  
 1st Qu.:  13.5578  
 Median :  17.2485  
 Mean   :  21.1732  
 3rd Qu.:  23.4287  
 Max.   :1300.0000  
 NA's   :13         </code></pre>
</div>
</div>
<p>Next, let’s plot this implicit interest rates by individual MFIs.</p>
<p>For this plot, it is</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb43"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb43-1"><a href="#cb43-1" aria-hidden="true" tabindex="-1"></a>df <span class="ot">&lt;-</span> <span class="fu">subset</span>(data, year <span class="sc">==</span> <span class="dv">2016</span>)</span>
<span id="cb43-2"><a href="#cb43-2" aria-hidden="true" tabindex="-1"></a><span class="fu">ggplot</span>(df, <span class="fu">aes</span>(<span class="at">x =</span> Abbreviation, <span class="at">y =</span> interest_rate)) <span class="sc">+</span></span>
<span id="cb43-3"><a href="#cb43-3" aria-hidden="true" tabindex="-1"></a>  <span class="fu">geom_bar</span>(<span class="at">stat =</span> <span class="st">"identity"</span>) <span class="sc">+</span></span>
<span id="cb43-4"><a href="#cb43-4" aria-hidden="true" tabindex="-1"></a>  <span class="fu">labs</span>(<span class="at">title =</span> <span class="st">"Interest Rates by MFI in 2016"</span>,</span>
<span id="cb43-5"><a href="#cb43-5" aria-hidden="true" tabindex="-1"></a>       <span class="at">x =</span> <span class="st">"MFI"</span>,</span>
<span id="cb43-6"><a href="#cb43-6" aria-hidden="true" tabindex="-1"></a>       <span class="at">y =</span> <span class="st">"Interest Rate"</span>) <span class="sc">+</span></span>
<span id="cb43-7"><a href="#cb43-7" aria-hidden="true" tabindex="-1"></a>  <span class="fu">theme_minimal</span>() <span class="sc">+</span> </span>
<span id="cb43-8"><a href="#cb43-8" aria-hidden="true" tabindex="-1"></a>  <span class="fu">theme</span>(<span class="at">axis.text.x =</span> <span class="fu">element_text</span>(<span class="at">angle =</span> <span class="sc">-</span><span class="dv">90</span>, <span class="at">hjust =</span> <span class="dv">0</span>, <span class="at">vjust =</span> <span class="dv">0</span>,<span class="at">size =</span> <span class="dv">5</span>))</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output-display">
<div>
<figure class="figure">
<p><img src="Tutorial-of-R--Docs-_files/figure-html/unnamed-chunk-18-1.png" class="img-fluid figure-img" width="672"></p>
</figure>
</div>
</div>
</div>
<p>We can also reorder the MFIs from low to high in interest rates as follow:</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb44"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb44-1"><a href="#cb44-1" aria-hidden="true" tabindex="-1"></a>df <span class="ot">&lt;-</span> <span class="fu">subset</span>(data, year <span class="sc">==</span> <span class="dv">2016</span>)</span>
<span id="cb44-2"><a href="#cb44-2" aria-hidden="true" tabindex="-1"></a><span class="fu">ggplot</span>(df, <span class="fu">aes</span>(<span class="at">x =</span> <span class="fu">reorder</span>(Abbreviation, interest_rate), <span class="at">y =</span> interest_rate)) <span class="sc">+</span></span>
<span id="cb44-3"><a href="#cb44-3" aria-hidden="true" tabindex="-1"></a>  <span class="fu">geom_bar</span>(<span class="at">stat =</span> <span class="st">"identity"</span>) <span class="sc">+</span></span>
<span id="cb44-4"><a href="#cb44-4" aria-hidden="true" tabindex="-1"></a>  <span class="fu">labs</span>(<span class="at">title =</span> <span class="st">"Interest Rates by MFI in 2016"</span>,</span>
<span id="cb44-5"><a href="#cb44-5" aria-hidden="true" tabindex="-1"></a>       <span class="at">x =</span> <span class="st">"MFI"</span>,</span>
<span id="cb44-6"><a href="#cb44-6" aria-hidden="true" tabindex="-1"></a>       <span class="at">y =</span> <span class="st">"Interest Rate"</span>) <span class="sc">+</span></span>
<span id="cb44-7"><a href="#cb44-7" aria-hidden="true" tabindex="-1"></a>  <span class="fu">theme_minimal</span>() <span class="sc">+</span> </span>
<span id="cb44-8"><a href="#cb44-8" aria-hidden="true" tabindex="-1"></a>  <span class="fu">theme</span>(<span class="at">axis.text.x =</span> <span class="fu">element_text</span>(<span class="at">angle =</span> <span class="sc">-</span><span class="dv">90</span>, <span class="at">hjust =</span> <span class="dv">0</span>, <span class="at">vjust =</span> <span class="dv">0</span>,<span class="at">size =</span> <span class="dv">5</span>))</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output-display">
<div>
<figure class="figure">
<p><img src="Tutorial-of-R--Docs-_files/figure-html/unnamed-chunk-19-1.png" class="img-fluid figure-img" width="672"></p>
</figure>
</div>
</div>
</div>
<p>We can also compare the interest rate between 2016 and 2017 for each MFI. <code>position = "dodge"</code> is used to place the bars for different years side by side for each bank.</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb45"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb45-1"><a href="#cb45-1" aria-hidden="true" tabindex="-1"></a>data_filtered <span class="ot">&lt;-</span> <span class="fu">subset</span>(data, year <span class="sc">%in%</span> <span class="fu">c</span>(<span class="dv">2016</span>, <span class="dv">2017</span>))</span>
<span id="cb45-2"><a href="#cb45-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb45-3"><a href="#cb45-3" aria-hidden="true" tabindex="-1"></a><span class="co"># Calculate the order of banks based on the interest rate in 2016</span></span>
<span id="cb45-4"><a href="#cb45-4" aria-hidden="true" tabindex="-1"></a>order_banks <span class="ot">&lt;-</span> data_filtered[data_filtered<span class="sc">$</span>year <span class="sc">==</span> <span class="dv">2016</span>, ]</span>
<span id="cb45-5"><a href="#cb45-5" aria-hidden="true" tabindex="-1"></a>order_banks <span class="ot">&lt;-</span> order_banks[<span class="fu">order</span>(order_banks<span class="sc">$</span>interest_rate), ]</span>
<span id="cb45-6"><a href="#cb45-6" aria-hidden="true" tabindex="-1"></a>ordered_levels <span class="ot">&lt;-</span> order_banks<span class="sc">$</span>Abbreviation</span>
<span id="cb45-7"><a href="#cb45-7" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb45-8"><a href="#cb45-8" aria-hidden="true" tabindex="-1"></a><span class="co"># Convert the bank column to a factor with ordered levels</span></span>
<span id="cb45-9"><a href="#cb45-9" aria-hidden="true" tabindex="-1"></a>data_filtered<span class="sc">$</span>Abbreviation <span class="ot">&lt;-</span> <span class="fu">factor</span>(data_filtered<span class="sc">$</span>Abbreviation, <span class="at">levels =</span> ordered_levels)</span>
<span id="cb45-10"><a href="#cb45-10" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb45-11"><a href="#cb45-11" aria-hidden="true" tabindex="-1"></a><span class="co"># Create the grouped bar plot</span></span>
<span id="cb45-12"><a href="#cb45-12" aria-hidden="true" tabindex="-1"></a><span class="fu">ggplot</span>(data_filtered, <span class="fu">aes</span>(<span class="at">x =</span> Abbreviation, <span class="at">y =</span> interest_rate, <span class="at">fill =</span> <span class="fu">factor</span>(year))) <span class="sc">+</span></span>
<span id="cb45-13"><a href="#cb45-13" aria-hidden="true" tabindex="-1"></a>  <span class="fu">geom_bar</span>(<span class="at">stat =</span> <span class="st">"identity"</span>, <span class="at">position =</span> <span class="st">"dodge"</span>) <span class="sc">+</span></span>
<span id="cb45-14"><a href="#cb45-14" aria-hidden="true" tabindex="-1"></a>  <span class="fu">labs</span>(<span class="at">title =</span> <span class="st">"Interest Rates by Bank in 2016 and 2017"</span>,</span>
<span id="cb45-15"><a href="#cb45-15" aria-hidden="true" tabindex="-1"></a>       <span class="at">x =</span> <span class="st">"MFI"</span>,</span>
<span id="cb45-16"><a href="#cb45-16" aria-hidden="true" tabindex="-1"></a>       <span class="at">y =</span> <span class="st">"Interest Rate"</span>,</span>
<span id="cb45-17"><a href="#cb45-17" aria-hidden="true" tabindex="-1"></a>       <span class="at">fill =</span> <span class="st">"Year"</span>) <span class="sc">+</span></span>
<span id="cb45-18"><a href="#cb45-18" aria-hidden="true" tabindex="-1"></a>  <span class="fu">theme_minimal</span>() <span class="sc">+</span> </span>
<span id="cb45-19"><a href="#cb45-19" aria-hidden="true" tabindex="-1"></a>  <span class="fu">theme</span>(<span class="at">axis.text.x =</span> <span class="fu">element_text</span>(<span class="at">angle =</span> <span class="sc">-</span><span class="dv">90</span>, <span class="at">hjust =</span> <span class="dv">0</span>, <span class="at">vjust =</span> <span class="dv">0</span>,<span class="at">size =</span> <span class="dv">5</span>))</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stderr">
<pre><code>Warning: Removed 1 row containing missing values or values outside the scale range
(`geom_bar()`).</code></pre>
</div>
<div class="cell-output-display">
<div>
<figure class="figure">
<p><img src="Tutorial-of-R--Docs-_files/figure-html/unnamed-chunk-20-1.png" class="img-fluid figure-img" width="672"></p>
</figure>
</div>
</div>
</div>
<section id="question" class="level4">
<h4 class="anchored" data-anchor-id="question"><em>Question</em></h4>
<p>Some MFIs show the increase in interest rates from 2016 to 2017, although there is a regulation of the interest rate cap. Why? Consider the problems in the measure of “implicit interest rate”? And propose another approach for analysis of impact of interest rate cap policy.</p>
<p>Hint: There could be multiple issues in the analysis. Consider as many as possible. One of the problems is based on the context of micro lending in Cambodia. And others are based on the definition of the variable.</p>
</section>
</section>
</section>
<section id="regression-analysis" class="level1">
<h1>Regression Analysis</h1>
<section id="ols-estimation" class="level2">
<h2 class="anchored" data-anchor-id="ols-estimation">OLS Estimation</h2>
<p>Making regression in R is very simple. We can do that by using lm() function.</p>
<p>We can type the codes as follow.</p>
<p><span class="math display">\[ y_{i} = \alpha + \beta x_i + \epsilon_i  \]</span></p>
<div class="cell">
<div class="sourceCode cell-code" id="cb47"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb47-1"><a href="#cb47-1" aria-hidden="true" tabindex="-1"></a>reg <span class="ot">&lt;-</span> <span class="fu">lm</span>( m_asset1 <span class="sc">~</span> staff, <span class="at">data=</span> data) </span>
<span id="cb47-2"><a href="#cb47-2" aria-hidden="true" tabindex="-1"></a><span class="fu">summary</span>(reg)</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stdout">
<pre><code>
Call:
lm(formula = m_asset1 ~ staff, data = data)

Residuals:
     Min       1Q   Median       3Q      Max 
-2994730    28711   112352   146917  8182090 

Coefficients:
              Estimate Std. Error t value Pr(&gt;|t|)    
(Intercept) -157225.58   21592.98  -7.281 7.69e-13 ***
staff          1222.26      19.46  62.808  &lt; 2e-16 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 583800 on 828 degrees of freedom
  (9 observations deleted due to missingness)
Multiple R-squared:  0.8265,    Adjusted R-squared:  0.8263 
F-statistic:  3945 on 1 and 828 DF,  p-value: &lt; 2.2e-16</code></pre>
</div>
</div>
<p>The results of estimated regression coefficients can be plotted by abline() function. After plotting the data of two variables in the graph, we can add the regression line using the results of regression as follow.</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb49"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb49-1"><a href="#cb49-1" aria-hidden="true" tabindex="-1"></a><span class="fu">plot</span>(data<span class="sc">$</span>staff, data<span class="sc">$</span>m_asset1)  <span class="co">#x axis comes in the first imput, and y axis comes in the second input. abline(reg,col=“red"")</span></span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output-display">
<div>
<figure class="figure">
<p><img src="Tutorial-of-R--Docs-_files/figure-html/unnamed-chunk-22-1.png" class="img-fluid figure-img" width="672"></p>
</figure>
</div>
</div>
</div>
<p>Coding the regression analysis in R is quite flexible. We can run the regression with log transformation of independent variables If we transform y and x variables in the log form, the regression model is expressed as below.</p>
<p><span class="math display">\[
\log(y_i) = \alpha + \beta + \log(x_i) + \epsilon_i
\]</span></p>
<p>The regression of the above mentioned model can be performed using the log function as follow.</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb50"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb50-1"><a href="#cb50-1" aria-hidden="true" tabindex="-1"></a>log_reg <span class="ot">&lt;-</span> <span class="fu">lm</span>( <span class="fu">log</span>(m_asset1 <span class="sc">+</span><span class="dv">1</span>) <span class="sc">~</span> <span class="fu">log</span>(staff <span class="sc">+</span><span class="dv">1</span>), <span class="at">data=</span>data) </span>
<span id="cb50-2"><a href="#cb50-2" aria-hidden="true" tabindex="-1"></a><span class="fu">summary</span>(log_reg)</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stdout">
<pre><code>
Call:
lm(formula = log(m_asset1 + 1) ~ log(staff + 1), data = data)

Residuals:
    Min      1Q  Median      3Q     Max 
-4.4350 -0.5725 -0.0261  0.5351  3.2044 

Coefficients:
               Estimate Std. Error t value Pr(&gt;|t|)    
(Intercept)     6.30249    0.09163   68.78   &lt;2e-16 ***
log(staff + 1)  0.94567    0.01972   47.95   &lt;2e-16 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 0.9323 on 828 degrees of freedom
  (9 observations deleted due to missingness)
Multiple R-squared:  0.7352,    Adjusted R-squared:  0.7349 
F-statistic:  2299 on 1 and 828 DF,  p-value: &lt; 2.2e-16</code></pre>
</div>
</div>
<p>Since the “asset2” include zero values and negative values, log transformation make “NA” as missing values. If the transformed variable contains “NA” or “inf”, the regression will return errors. In that case, we should transform variables in advance and should code the variables not including NA and inf before the analysis.</p>
<p>log transformation can be also used in plot function.</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb52"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb52-1"><a href="#cb52-1" aria-hidden="true" tabindex="-1"></a><span class="fu">plot</span>(<span class="fu">log</span>(data<span class="sc">$</span>m_asset2), <span class="fu">log</span>(data<span class="sc">$</span>m_asset1)) </span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output-display">
<div>
<figure class="figure">
<p><img src="Tutorial-of-R--Docs-_files/figure-html/unnamed-chunk-24-1.png" class="img-fluid figure-img" width="672"></p>
</figure>
</div>
</div>
</div>
</section>
</section>

</main>
<!-- /main column -->
<script id="quarto-html-after-body" type="application/javascript">
window.document.addEventListener("DOMContentLoaded", function (event) {
  const toggleBodyColorMode = (bsSheetEl) => {
    const mode = bsSheetEl.getAttribute("data-mode");
    const bodyEl = window.document.querySelector("body");
    if (mode === "dark") {
      bodyEl.classList.add("quarto-dark");
      bodyEl.classList.remove("quarto-light");
    } else {
      bodyEl.classList.add("quarto-light");
      bodyEl.classList.remove("quarto-dark");
    }
  }
  const toggleBodyColorPrimary = () => {
    const bsSheetEl = window.document.querySelector("link#quarto-bootstrap");
    if (bsSheetEl) {
      toggleBodyColorMode(bsSheetEl);
    }
  }
  toggleBodyColorPrimary();  
  const icon = "";
  const anchorJS = new window.AnchorJS();
  anchorJS.options = {
    placement: 'right',
    icon: icon
  };
  anchorJS.add('.anchored');
  const isCodeAnnotation = (el) => {
    for (const clz of el.classList) {
      if (clz.startsWith('code-annotation-')) {                     
        return true;
      }
    }
    return false;
  }
  const clipboard = new window.ClipboardJS('.code-copy-button', {
    text: function(trigger) {
      const codeEl = trigger.previousElementSibling.cloneNode(true);
      for (const childEl of codeEl.children) {
        if (isCodeAnnotation(childEl)) {
          childEl.remove();
        }
      }
      return codeEl.innerText;
    }
  });
  clipboard.on('success', function(e) {
    // button target
    const button = e.trigger;
    // don't keep focus
    button.blur();
    // flash "checked"
    button.classList.add('code-copy-button-checked');
    var currentTitle = button.getAttribute("title");
    button.setAttribute("title", "Copied!");
    let tooltip;
    if (window.bootstrap) {
      button.setAttribute("data-bs-toggle", "tooltip");
      button.setAttribute("data-bs-placement", "left");
      button.setAttribute("data-bs-title", "Copied!");
      tooltip = new bootstrap.Tooltip(button, 
        { trigger: "manual", 
          customClass: "code-copy-button-tooltip",
          offset: [0, -8]});
      tooltip.show();    
    }
    setTimeout(function() {
      if (tooltip) {
        tooltip.hide();
        button.removeAttribute("data-bs-title");
        button.removeAttribute("data-bs-toggle");
        button.removeAttribute("data-bs-placement");
      }
      button.setAttribute("title", currentTitle);
      button.classList.remove('code-copy-button-checked');
    }, 1000);
    // clear code selection
    e.clearSelection();
  });
    var localhostRegex = new RegExp(/^(?:http|https):\/\/localhost\:?[0-9]*\//);
    var mailtoRegex = new RegExp(/^mailto:/);
      var filterRegex = new RegExp('/' + window.location.host + '/');
    var isInternal = (href) => {
        return filterRegex.test(href) || localhostRegex.test(href) || mailtoRegex.test(href);
    }
    // Inspect non-navigation links and adorn them if external
 	var links = window.document.querySelectorAll('a[href]:not(.nav-link):not(.navbar-brand):not(.toc-action):not(.sidebar-link):not(.sidebar-item-toggle):not(.pagination-link):not(.no-external):not([aria-hidden]):not(.dropdown-item):not(.quarto-navigation-tool)');
    for (var i=0; i<links.length; i++) {
      const link = links[i];
      if (!isInternal(link.href)) {
        // undo the damage that might have been done by quarto-nav.js in the case of
        // links that we want to consider external
        if (link.dataset.originalHref !== undefined) {
          link.href = link.dataset.originalHref;
        }
      }
    }
  function tippyHover(el, contentFn, onTriggerFn, onUntriggerFn) {
    const config = {
      allowHTML: true,
      maxWidth: 500,
      delay: 100,
      arrow: false,
      appendTo: function(el) {
          return el.parentElement;
      },
      interactive: true,
      interactiveBorder: 10,
      theme: 'quarto',
      placement: 'bottom-start',
    };
    if (contentFn) {
      config.content = contentFn;
    }
    if (onTriggerFn) {
      config.onTrigger = onTriggerFn;
    }
    if (onUntriggerFn) {
      config.onUntrigger = onUntriggerFn;
    }
    window.tippy(el, config); 
  }
  const noterefs = window.document.querySelectorAll('a[role="doc-noteref"]');
  for (var i=0; i<noterefs.length; i++) {
    const ref = noterefs[i];
    tippyHover(ref, function() {
      // use id or data attribute instead here
      let href = ref.getAttribute('data-footnote-href') || ref.getAttribute('href');
      try { href = new URL(href).hash; } catch {}
      const id = href.replace(/^#\/?/, "");
      const note = window.document.getElementById(id);
      if (note) {
        return note.innerHTML;
      } else {
        return "";
      }
    });
  }
  const xrefs = window.document.querySelectorAll('a.quarto-xref');
  const processXRef = (id, note) => {
    // Strip column container classes
    const stripColumnClz = (el) => {
      el.classList.remove("page-full", "page-columns");
      if (el.children) {
        for (const child of el.children) {
          stripColumnClz(child);
        }
      }
    }
    stripColumnClz(note)
    if (id === null || id.startsWith('sec-')) {
      // Special case sections, only their first couple elements
      const container = document.createElement("div");
      if (note.children && note.children.length > 2) {
        container.appendChild(note.children[0].cloneNode(true));
        for (let i = 1; i < note.children.length; i++) {
          const child = note.children[i];
          if (child.tagName === "P" && child.innerText === "") {
            continue;
          } else {
            container.appendChild(child.cloneNode(true));
            break;
          }
        }
        if (window.Quarto?.typesetMath) {
          window.Quarto.typesetMath(container);
        }
        return container.innerHTML
      } else {
        if (window.Quarto?.typesetMath) {
          window.Quarto.typesetMath(note);
        }
        return note.innerHTML;
      }
    } else {
      // Remove any anchor links if they are present
      const anchorLink = note.querySelector('a.anchorjs-link');
      if (anchorLink) {
        anchorLink.remove();
      }
      if (window.Quarto?.typesetMath) {
        window.Quarto.typesetMath(note);
      }
      // TODO in 1.5, we should make sure this works without a callout special case
      if (note.classList.contains("callout")) {
        return note.outerHTML;
      } else {
        return note.innerHTML;
      }
    }
  }
  for (var i=0; i<xrefs.length; i++) {
    const xref = xrefs[i];
    tippyHover(xref, undefined, function(instance) {
      instance.disable();
      let url = xref.getAttribute('href');
      let hash = undefined; 
      if (url.startsWith('#')) {
        hash = url;
      } else {
        try { hash = new URL(url).hash; } catch {}
      }
      if (hash) {
        const id = hash.replace(/^#\/?/, "");
        const note = window.document.getElementById(id);
        if (note !== null) {
          try {
            const html = processXRef(id, note.cloneNode(true));
            instance.setContent(html);
          } finally {
            instance.enable();
            instance.show();
          }
        } else {
          // See if we can fetch this
          fetch(url.split('#')[0])
          .then(res => res.text())
          .then(html => {
            const parser = new DOMParser();
            const htmlDoc = parser.parseFromString(html, "text/html");
            const note = htmlDoc.getElementById(id);
            if (note !== null) {
              const html = processXRef(id, note);
              instance.setContent(html);
            } 
          }).finally(() => {
            instance.enable();
            instance.show();
          });
        }
      } else {
        // See if we can fetch a full url (with no hash to target)
        // This is a special case and we should probably do some content thinning / targeting
        fetch(url)
        .then(res => res.text())
        .then(html => {
          const parser = new DOMParser();
          const htmlDoc = parser.parseFromString(html, "text/html");
          const note = htmlDoc.querySelector('main.content');
          if (note !== null) {
            // This should only happen for chapter cross references
            // (since there is no id in the URL)
            // remove the first header
            if (note.children.length > 0 && note.children[0].tagName === "HEADER") {
              note.children[0].remove();
            }
            const html = processXRef(null, note);
            instance.setContent(html);
          } 
        }).finally(() => {
          instance.enable();
          instance.show();
        });
      }
    }, function(instance) {
    });
  }
      let selectedAnnoteEl;
      const selectorForAnnotation = ( cell, annotation) => {
        let cellAttr = 'data-code-cell="' + cell + '"';
        let lineAttr = 'data-code-annotation="' +  annotation + '"';
        const selector = 'span[' + cellAttr + '][' + lineAttr + ']';
        return selector;
      }
      const selectCodeLines = (annoteEl) => {
        const doc = window.document;
        const targetCell = annoteEl.getAttribute("data-target-cell");
        const targetAnnotation = annoteEl.getAttribute("data-target-annotation");
        const annoteSpan = window.document.querySelector(selectorForAnnotation(targetCell, targetAnnotation));
        const lines = annoteSpan.getAttribute("data-code-lines").split(",");
        const lineIds = lines.map((line) => {
          return targetCell + "-" + line;
        })
        let top = null;
        let height = null;
        let parent = null;
        if (lineIds.length > 0) {
            //compute the position of the single el (top and bottom and make a div)
            const el = window.document.getElementById(lineIds[0]);
            top = el.offsetTop;
            height = el.offsetHeight;
            parent = el.parentElement.parentElement;
          if (lineIds.length > 1) {
            const lastEl = window.document.getElementById(lineIds[lineIds.length - 1]);
            const bottom = lastEl.offsetTop + lastEl.offsetHeight;
            height = bottom - top;
          }
          if (top !== null && height !== null && parent !== null) {
            // cook up a div (if necessary) and position it 
            let div = window.document.getElementById("code-annotation-line-highlight");
            if (div === null) {
              div = window.document.createElement("div");
              div.setAttribute("id", "code-annotation-line-highlight");
              div.style.position = 'absolute';
              parent.appendChild(div);
            }
            div.style.top = top - 2 + "px";
            div.style.height = height + 4 + "px";
            div.style.left = 0;
            let gutterDiv = window.document.getElementById("code-annotation-line-highlight-gutter");
            if (gutterDiv === null) {
              gutterDiv = window.document.createElement("div");
              gutterDiv.setAttribute("id", "code-annotation-line-highlight-gutter");
              gutterDiv.style.position = 'absolute';
              const codeCell = window.document.getElementById(targetCell);
              const gutter = codeCell.querySelector('.code-annotation-gutter');
              gutter.appendChild(gutterDiv);
            }
            gutterDiv.style.top = top - 2 + "px";
            gutterDiv.style.height = height + 4 + "px";
          }
          selectedAnnoteEl = annoteEl;
        }
      };
      const unselectCodeLines = () => {
        const elementsIds = ["code-annotation-line-highlight", "code-annotation-line-highlight-gutter"];
        elementsIds.forEach((elId) => {
          const div = window.document.getElementById(elId);
          if (div) {
            div.remove();
          }
        });
        selectedAnnoteEl = undefined;
      };
        // Handle positioning of the toggle
    window.addEventListener(
      "resize",
      throttle(() => {
        elRect = undefined;
        if (selectedAnnoteEl) {
          selectCodeLines(selectedAnnoteEl);
        }
      }, 10)
    );
    function throttle(fn, ms) {
    let throttle = false;
    let timer;
      return (...args) => {
        if(!throttle) { // first call gets through
            fn.apply(this, args);
            throttle = true;
        } else { // all the others get throttled
            if(timer) clearTimeout(timer); // cancel #2
            timer = setTimeout(() => {
              fn.apply(this, args);
              timer = throttle = false;
            }, ms);
        }
      };
    }
      // Attach click handler to the DT
      const annoteDls = window.document.querySelectorAll('dt[data-target-cell]');
      for (const annoteDlNode of annoteDls) {
        annoteDlNode.addEventListener('click', (event) => {
          const clickedEl = event.target;
          if (clickedEl !== selectedAnnoteEl) {
            unselectCodeLines();
            const activeEl = window.document.querySelector('dt[data-target-cell].code-annotation-active');
            if (activeEl) {
              activeEl.classList.remove('code-annotation-active');
            }
            selectCodeLines(clickedEl);
            clickedEl.classList.add('code-annotation-active');
          } else {
            // Unselect the line
            unselectCodeLines();
            clickedEl.classList.remove('code-annotation-active');
          }
        });
      }
  const findCites = (el) => {
    const parentEl = el.parentElement;
    if (parentEl) {
      const cites = parentEl.dataset.cites;
      if (cites) {
        return {
          el,
          cites: cites.split(' ')
        };
      } else {
        return findCites(el.parentElement)
      }
    } else {
      return undefined;
    }
  };
  var bibliorefs = window.document.querySelectorAll('a[role="doc-biblioref"]');
  for (var i=0; i<bibliorefs.length; i++) {
    const ref = bibliorefs[i];
    const citeInfo = findCites(ref);
    if (citeInfo) {
      tippyHover(citeInfo.el, function() {
        var popup = window.document.createElement('div');
        citeInfo.cites.forEach(function(cite) {
          var citeDiv = window.document.createElement('div');
          citeDiv.classList.add('hanging-indent');
          citeDiv.classList.add('csl-entry');
          var biblioDiv = window.document.getElementById('ref-' + cite);
          if (biblioDiv) {
            citeDiv.innerHTML = biblioDiv.innerHTML;
          }
          popup.appendChild(citeDiv);
        });
        return popup.innerHTML;
      });
    }
  }
});
</script>
</div> <!-- /content -->




</body></html>

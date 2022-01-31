# Lab 03 Report - Documentation and Community

## Part 1 - Documentation

### Wiki page

Link to wiki page can be found [here](https://github.com/emkulka/oss-repo-template/wiki/Project-Ideas).

### LaTex formulae

the LaTex code `$\sqrt{1+2\sqrt{1+3\sqrt{1+4\sqrt{1+...}}}}$` produces <img src="https://user-images.githubusercontent.com/25308429/151391932-9c4b5df6-4cc1-480e-9aee-e38f387308b7.png" width="200" height="50" />

the LaTex code `$\sqrt{2}^{\sqrt{2}^{\sqrt{2}^{\sqrt{2}^{...}}}}$` produces <img src="https://user-images.githubusercontent.com/25308429/151392118-9310027a-591e-4bd1-9b13-cc5cc3564b94.png" width="100" height="50" />

### LaTex Hadamard Matrix

the LaTex code
```
$\begin{bmatrix}
1 & 1 & 1 & 1 \\
-1 & 1 & -1 & 1 \\
-1 & -1 & 1 & 1 \\
1 & -1 & -1 & 1
\end{bmatrix}$
```
produces

<img src="https://user-images.githubusercontent.com/25308429/151393768-aa9ebe82-86ab-42af-9420-616cd9b6e321.png" width="100" height="75" />

## Part 2 - Community

### RCOS Projects

| Project Name | contributors | lines of code | first commit | latest commit | current branches |
| --- | --- | --- | --- | --- | --- |
| ARAS | 1 |  56794 | 4da6754 09/22/2015 | 8cf1d31 12/04/2017 | master |
| Aris | 14 | 13118 | 69945fe 04/05/2017 | 03819f8 10/22/2021 | master, Key_Palette, proof-generate-solver, Disjunctive_syllogism, gh-pages|
| Article Aggregator | 2 | 543,664 | a3e586a 09/20/2019 | 0f8d55a 12/10/2019 | master |
| Astro.IQ | 1| 195608| bc1107c 01/28/2017 | 4e2df67 05/03/2017 | master, renovate/configure|

### GitStats

<img src="https://user-images.githubusercontent.com/25308429/151599279-afc127a1-428f-4faf-bb81-6c3b906c5a59.png" width="400" height="350" />

<img src="https://user-images.githubusercontent.com/25308429/151602650-be99c495-3e8a-4347-9ce6-b0ab9fcd8a14.png" width="400" height="300" />

<img src="https://user-images.githubusercontent.com/25308429/151602103-13a1afed-4bb0-4f65-9fc0-d813f4252593.png" width="400" height="300" />

<img src="https://user-images.githubusercontent.com/25308429/151602294-19e82748-cb0b-4781-acfd-0e1cb1f80d05.png" width="400" height="300" />

One difference we noticed between what we found and what GitStats produced was the number of lines of code. Running the command `git ls-files -z | xargs -0 wc -l` provides all the lines in all files in the repository, whereas GitStats only looks at the lines of true code. 

In general, we noticed that it is not common for these open source projects to have more than a few contributors. This is likely because even though you may be passionate about a certain project, it can be challenging to get others interested enough that they would also want to contribute.

### gource
The following is what occured when I tried to run gource on ARAS:

<img src="https://user-images.githubusercontent.com/25308429/151829373-ae6bb918-5aea-4908-b090-3159b5ea2058.png" />

This is a screenshot from a tablemate who was able to run gource on Article Aggregator

<img src="https://user-images.githubusercontent.com/25308429/151709903-ad8bfc49-77f1-43b3-ad27-8b7c9e7d63e2.png" width="400" height="300" />


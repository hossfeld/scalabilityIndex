# Computation of Confidence Intervals for the Scalability Index 

---
>(c) Tobias Hossfeld (2026).
>
>The scripts are computing the confidence interval for the scalability index, which is defined in the following publication. Please cite upon usage:
> *Hossfeld, T., Heegaard, P. E., & Kellerer, W. (2023). Comparing the scalability of communication networks and systems. IEEE Access, 11, 101474-101497, [DOI 10.1109/ACCESS.2023.3314201](https://doi.org/10.1109/ACCESS.2023.3314201).*
---
## Jupyter Notebook `scalabilityIndexConfidenceIntervals.ipynb`
This Jupyter notebook aims at demonstrating the computation of confidence intervals for the scalability index. Therefore, we generate synthetic measurement data for a given set of parameter values. For each parameter value, multiple measurement runs are created based on the underlying system function and additional random variability that mimics measurement noise and experimental uncertainty. Depending on the scenario, either a fixed or a random number of measurement runs can be generated for each parameter value.

Next, the **Scalability Index (SI)** is computed from the generated measurement data. The Scalability Index is a single-value metric that quantifies the scalability of a system (system under test, SUT) by comparing its behavior to that of a reference system (REF) over a specified parameter range. A target measure of interest, such as response time, throughput, availability, or failure rate, is described by a system function ($f(x)$), while the reference system is characterized by a reference function ($h(x)$). The parameter range under investigation can be weighted to reflect the importance or frequency of different operating conditions. The SI is then computed as the ratio of the weighted integral measurements (i.e., the weighted areas $F$ and $H$ under the system and reference curves), adjusted by a goodness indicator ($\gamma$), which accounts for whether larger values of the target measure are desirable ($\gamma=1$) or undesirable ($\gamma=-1$). As a result, the SI provides a normalized measure of how well the system scales relative to the chosen reference. More details can be found in [Hossfeld, T., Heegaard, P. E., & Kellerer, W. (2023). Comparing the scalability of communication networks and systems. IEEE Access, 11, 101474-101497](https://doi.org/10.1109/ACCESS.2023.3314201).

$$
SI = \left( \frac{F}{H}\right)^{\displaystyle \gamma} = \left( \frac{ \int_{a}^{b} f(x) \cdot w(x) \;dx }{ \int_{a}^{b} h(x) \cdot w(x) \;dx }\right)^{\displaystyle  \gamma}
$$

Finally, confidence intervals for the Scalability Index are estimated. These intervals quantify the statistical uncertainty of the SI estimate and provide a measure of confidence in the computed scalability assessment. The resulting confidence intervals allow evaluating whether observed differences in scalability are statistically significant and how robust the scalability conclusions are with respect to measurement variability and limited sample sizes.

# Discrete-time MCC-KF and IMCC-KF implementation methods
This repository contains MATLAB functions with various implementation methods of the Maximum Correntropy Criterion Kalman Filter (MCC-KF) by Izanloo et.al. (2016, <a href="https://doi.org/10.1109/CISS.2016.7460553">DOI</a>) and improved MCC-KF (IMCC-KF) by Kulikova (2017, <a href="https://doi.org/10.1016/j.sysconle.2017.07.016">DOI</a>) with a scalar adjusting parameters. They are given in a posteriori form, i.e., no data are assumed to be known at the initial step and, hence, the time update comes first.
# References
Each code (implementation method) includes the exact reference where the particular algorithm was published. 
If you use these codes in your research, please, cite the corresponding articles mentioned in the codes.  

# Remark
The codes have been presented here for their instructional value only. They have been tested with care but are not guaranteed to be free of error and, hence, they should not be relied on as the sole basis to solve problems. 

# Steps to reproduce
- `Test_MCCKFs` is the script that performs Monte Carlo runs for solving filtering problem by various MCC-KF implementations.
- `Test_IMCCKFs` is the script that performs Monte Carlo runs for solving filtering problem by various IMCC-KF implementations.
- `Test_PI` is the script for calculating the Performance Index (Baram Proximity Measure) by various filtering algorithms. 
- `Illustrate_XP` is the script that illustrates the obtained estimates and the diagonal entries of the error covariance matrix (over time). You can find its call at the end of the script above, which is commented. Just delete this comment sign.
- `Illustrate_PI` is the script that illustrates the Performance Index (Baram Proximity Measure) calculated by various filtering algorithms. 
- `Simulate_Measurements` stands for simulating the state-space model and generating the measurements for the filtering methods.

When the state is estimated, the resulted errors of the MCC-KF implementation methods should be the same because they are mathematically equivalent to each other. Their numerical properties differ, but the ill-conditioned test examples are not given here. Similarly, the resulted errors of the IMCC-KF implementation methods should be the same because they are mathematically equivalent to each other. 

## List of the MCC-KF implementation methods
- Conventional algorithms:
 -  `Riccati_MCCKF` is the original implementation by Izanloo et.al. (2016, <a href="https://doi.org/10.1109/CISS.2016.7460553">DOI</a>)
- Square-root Cholesky factorization-based methods:
 -  `Riccati_MCCKF_SRCF_QR`   is the Square-Root Covariance Filter (SRCF) with upper triangular factors by Kulikova (2019), <a href="https://doi.org/10.1016/j.sigpro.2019.03.003">DOI</a> 
 -  `Riccati_MCCKF_SRCF_QL`   is the SRCF with lower triangular factors by Kulikova (2020), <a href="https://doi.org/10.1016/j.ifacol.2020.12.264">DOI</a>
 -  `Riccati_MCCKF_rSRCF_QL`  is the robust SRCF with lower triangular factors by Kulikova (2020), <a href="https://doi.org/10.1016/j.ifacol.2020.12.264">DOI</a> 
- Square-root SVD factorization-based methods:
 -  `Riccati_MCCKF_SVD`    is the SVD-based Covariance Filter by Kulikova (2019), <a href="https://doi.org/10.1016/j.sigpro.2019.03.003">DOI</a>
 -  `Riccati_MCCKF_rSVD`   is the robust SVD-based Covariance Filter by Kulikova (2019), <a href="https://doi.org/10.1016/j.sigpro.2019.03.003">DOI</a>

## List of the IMCC-KF implementation methods

# fe_black_litterman_opt
Portfolio weight allocation using the Black Litterman model.

# 


<!-- PROJECT LOGO -->
<br />
<div align="center">
  <h3 align="center">FE_BLACK_LITTERMAN_OPT: Basic implementation of the Black-Litterman model.</h3>

  <p align="center">
    "A portfolio allocation model that begins with modern portfolio theory (MPT) and adds in investor views of expected returns."
    <br />
  </p>
</div>



<!-- ABOUT THE PROJECT -->
## Modern Portfolio Theory (MPT): A high level primer

> The modern portfolio theory (MPT) is a practical method for selecting investments in order to maximize their overall returns within an acceptable level of risk. This mathematical framework is used to build a portfolio of investments that maximize the amount of expected return for the collective given level of risk.

Source: [Modern Portfolio Theory: What MPT Is and How Investors Use It](https://www.investopedia.com/terms/m/modernportfoliotheory.asp)

## Black-Litterman Model

The Black-Litterman Model extends MPT, and starts with an assumption of market equilibrium and then incorporates the views of the portfolio manager regarding the relative returns of individual assets. The views are expressed as "overweight" or "underweight" positions relative to the market portfolio. The model then adjusts the expected returns of individual assets using a Bayesian estimation process, taking into account the views and a measure of uncertainty around those views.

The final result is a set of optimal portfolio weights that incorporates both market equilibrium and the portfolio manager's views. This approach can lead to more robust and efficient portfolios than those produced by traditional mean-variance optimization, which only considers market equilibrium.

### Implementation (MATLAB)

`blacklitterman.m` outlines a simple example in which we develop an implement the Black-Litterman model to generate a set of portfolio weight allocations. A high level walkthrough of the steps taken are as follows:

1. Calculate the expected return, covariance matrix, and the implied equilibrium vector `pi` of the portfolio based on market capitalization weights, returns and the risk-free rate.
2. Incorporate views expressed by investors into the model. Three views are specified, each with a corresponding level of confidence (best, middle, worst scenarios). Build the view vector `Q` and the vector `p` that matches the views to the assets. A scaling constant `tau` is chosen and used to calculate the variance of the views, which is stored in the matrix `omega`. The new combined return vector, which takes into account both the prior knowledge and the views, is then calculated using the Black-Litterman formula.
3. Implement an intuitive approach to the Black-Litterman model. Calculate (in-order):
  * The return of the portfolio based on the views.
  * The weights of the portfolio based on the new return. 
  * The deviation of the new weights from the market capitalization weights. 
  * The tilt required to bring the portfolio in line with the views. 
  * The target weights of the portfolio, which takes into account both the market capitalization weights and the tilt. 
  * The variance of the views, which is used in the Black-Litterman formula.

---

<sup><sub>Porting over from local files, circa 2016-17.</sub></sup>

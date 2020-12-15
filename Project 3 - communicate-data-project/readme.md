# Loan Data from Prosper Exploration
## by Khaled Belal

## Dataset

> This data set contains 113,937 loans with 81 variables on each 
loan, including loan amount, borrower rate (or interest rate), 
current loan status, borrower income, and many others.

### I wanted to answer these questions

<ol>
<li>What factors affect a loan’s outcome status?

<li>What about the APR?

<li>What happents to the features over the years?
</ol>

## Summary of Findings


### Univariate Exploration
> About the plot **relation between the number of loans and Listingdate years/months/days**
>> We notice that the loans was **the highest on 2013** and **lowest on 2005**

> For **the relationship between the number of loans and Term** 

>> about **77%** of the **Term values** are **36**

>> and about **21.6%** of the **Term values** are **36**

>> and about **1.4%** of the **Term values** are **12**

> For the **hysteresis of the numerical variables \nBorrowerAPR , BorrowerRate and EstimatedEffectiveYield**

>> The previous graph is **Logical**, as the values are  **float** so **the bars will intersect** and we can see that 

>> About **5%** of the **Borrower values** are **0.36** 
and the rest **95%** are between **.05 and 0.4** all of them count less than 3000

>> About **5%** of the **BorrowerRate values** are **0.32** 
and the rest **95%** are between **.05 and 0.3** all of them count less than 4000

>> About **25.5%** of the **EstimatedEffectiveYield values** are **0** 
and the rest **74.5%** are between **.05 and 0.3199** all of them count less than 5000

> For the **hysteresis of the StatedMonthlyIncome for the loans between 0 and 100000**

>> Most borrowers have a monthly income of around 5,000. 

>> This distribution is right skewed with some long tails

>> only 17 borrower a monthly income have more than 100000

> For the **hysteresis of the MonthlyLoanPayment**

>> Most loans paidmonthly income of around 100-400, with a spike at 200. 

>> This distribution is right skewed

>> The reason why the number most monthly paid load is higher when the payemet is low, because most loan values are low 
(Less than 5000) which means the payment are low too

>> It's logical that there are about a 1000 loans which has 0 monthly payment, because some **big** loans have payments schadualed quarter yearly or even yearly

> For the **hysteresis of the LoanOriginalAmount**

>> Most loans are around 1000 to 7000, with a spikes at arount 4000, 11000,16000 .

>> The spikes represent arount 35% of the number of loans

>> This distribution is right skewed wth long tail

> For the **Number of loans count if borrrower is home owner**

>> Half the borrowers are home owners 

>> Half the borrowers don't own a home

> For the **the relation between the number of loans and ProsperRating**

>> The  Prosper Rating assigned at the time the listing was created: 0 - N/A, 1 - HR, 2 - E, 3 - D, 4 - C, 5 - B, 6 - A, 7 - AA.  Applicable for loans originated after July 2009.

>> The highest rate number of loans is C and the lowest number rate is  AA

>> For the **Number of loans count according to EmploymentStatus**

>> About 59% of the borrowers are Employed 

>> About 23% of the borrowers are Retired

>> About 7% of the borrowers EmploymentStatus are not available

>> About 5% of the borrowers are Self-employed

>> About 1% of the borrowers are not Employed

>> About 1% of the borrowers are Retired

>> About 1% of the borrowers are Part-Time

#### Discuss the distribution(s) of your variable(s) of interest. Were there any unusual points? Did you need to perform any transformations?

>the value reaches 1750000, which is very hard to plot at will result in a usless figure

>but we know for a fact that only 17 borrowers with more than 100000 monthly income

>We ploted only the loans that their borrowers have less than 100000 income 

> then we plotted the same graph wiith a logscale for a better visualization

#### Of the features you investigated, were there any unusual distributions? Did you perform any operations on the data to tidy, adjust, or change the form of the data? If so, why did you do this?

> **For Borrow APR**, we will rwplace NaN with the mean, a it will represent a suitable value for the **Annual Percentage Rate** if we took it along the whole period

> **For EstimatedEffectiveYield**, we will replace NaN with 0, because the NaN represented the loans before 2009 when those variables were not caculated

> **For ProsperRating (Alpha)**, we will replace NaN with N/A, because the NaN represented the loans before 2009 when those variables were not caculated

> **EmploymentStatus**, all the nan values were replaced by **not available**, as some workers tend to leave the cell 
embty when they don't have information about omething and what it means with **not available** 


### Bivariate Exploration

> For the **The correletion plot between all the numerical features**

>> most of the features don't have strong relationship between eachother

>> only five features have high effect each other:

>>> BorrowerAPR with BorrowerRate with EstimatedEffectiveYield

>>> MonthlyLoanPayment with LoanOriginalAmount



> For the **the Matrix plot (scatter) between all the numerical features**

>> most of the features don't have strong relationship between eachother

>> only five features have high effect each other:

>>> BorrowerAPR with BorrowerRate with EstimatedEffectiveYield

>>> MonthlyLoanPayment with LoanOriginalAmount


> For the **plot matrix (box plot) of numeric features against categorical features**

>> For the **Term Feature**

>>> All Borrowers are home owners

>>> Most Borrowers have ProsperRate D - C - B with equal anounts

>>> Most Borrowers with **high Term*** are home owners


>> For the **BorrowAPR and BorrowRate Features**

>>> Not home owner > home owners 

>>> For ProsperRate, **HR** >  **E** > **D** > **Not Rated** > **C** > **B** > **A** > **AA**

>>> For EmploymentSatus, **Not employed** > **other** > **Self-Employed** >   **retired**> **Employed**  >  **full-time** > **not available**  > **Part-time**


>> For the **EstimatedEffectiveYield Feature**

>>> Not home owner > home owners 

>>> For ProsperRate, **HR** >  **E** > **D** > **C** > **B** > **A** > **AA**

>>>> No **Not Rated Rate** maybe it was very low before 2009

>>> For EmploymentSatus, **Not employed** > **other** > **Self-Employed** >   **retired**> **Employed**  >  **full-time** > **Part-time** > **not available** 


>> For the **StatedMonthlyIncome Feature**

>>> All boxes are at zero with tall tails


>> For the **MonthlyLoanPayment and LoanOiginalAmount Features**

>>> Both features has similar shapes and they hold similar bositions but the **LoanOiginalAmount Feature** is bigger 

>>> For homowners, most borrowers and the biggest borrowesr are home home owners but the an values are  

>>> For ProsperRate, **AA rate** has the the highest of all loans, then  **B - C - A rates** have nearly similar values,
then **D** then **Not Rated** then **E** then **HR**

>>> For EmploymentSatus,**Employed** > **Self-Employed** > **other** > **full-time** > **not available** > **Not employed** > **retired** > **Part-time**



> For the **plot catigorical features against categorical features**

>> The ProsperRate with highest count is **0** which rpresent the loans before 2009

>> The lower the ProsperRate the higher the count eccept foor the C and B ProperRate as they spike greatly 

>> And as expected the employed, Fll-time and self-employed hold the most counts 
but it is not ordinal feature so we can't really specify a linear increament as in prosper rate



> For the **point plot of numeric features change over the years**

>> There are three features increases with years Like:
>>> Term, MonthhlyLoanPayment, LoanOriginalAmount, EstimatedEffectiveYield

>> There are three features Decrease with years Like:
>>> StatedMothlyIncome, BorrowAPR, BorrowRate

>> Most the feature spike up specially at 2011 and 2012

>> BorrowAPR, BorrowRate and EstimatedEffectiveYield decrease greatly after 2011

>> All the feature up or down spike happens around 2007, 2009, 2011 and 2012


> For the **violin plot of numeric features against RrosperRating**

>> For the **Term Feature**

>>> For the rates **E,D,C,B,A,AA**, the term is **highest** 

>>> For the rates **NotRated**, the term is **lowest** 

>>> For the rate **HR**, the term is same level as the others but it doesn't increase or decrease 


>> For the **BorrowAPR and BorrowRate Features**

>>> For the rate **HR**, the term has the biggest range but the lowest number 

>>> The other rates are as following, **HR** >  **E** > **D** > **C** > **B** > **A** > **AA**


>> For the **EstimatedEffectiveYield Feature**

>>> For the rate **Not Rated**, the term is same level as the others but it doesn't increase or decrease

>>> The other rates are as following, **HR** >  **E** > **D** > **C** > **B** > **A** > **AA** 


>> For the **StatedMonthlyIncome Feature**

>>> For the rate **C,B,A,AA**, the term is same level and the same range wich is the highest of the other rates

>>> For the rate **HR,E,D**, the term is same level and the same range which is the second highest of the other rates

>>> For the rate **Not Rated**, the term is same level and the same range which is the third highest of the other rates

>>> For the rate **HR,E**, the term is same level a and same range which is the lowest of the other rates


>> For the **MonthlyLoanPayment and LoanOiginalAmount Features**

>>> For the rate **B,A,AA**, the term is same level and the same range wich is the highest of the other rates

>>> For the rate **HR,E,D**, the term is same level and the same range which is the second highest of the other rates

>>> For the rate **Not Rated,C**, the term is same level a and same range which is the lowest of the other rates



#### Talk about some of the relationships you observed in this part of the investigation. How did the feature(s) of interest vary with other features in the dataset?

>> The ProsperRate with highest count is **0** which rpresent the loans before 2009

>> The lower the ProsperRate the higher the count eccept foor the C and B ProperRate as they spike greatly 

>> And as expected the employed, Fll-time and self-employed hold the most counts 
but it is not ordinal feature so we can't really specify a linear increament as in prosper rate


#### Did you observe any interesting relationships between the other features (not the main feature(s) of interest)?

>> Most the feature spike up specially at 2011 and 2012

>> BorrowAPR, BorrowRate and EstimatedEffectiveYield decrease greatly after 2011

>> All the feature up or down spike happens around 2007, 2009, 2011 and 2012


### Multivariate Exploration

> We will focus on the relationship between

>> The numerical features: LoanOriginalAmount and BorrowerAPR 
> **with the** 
>> The catagorical: ProsperRating and EmploymentStatus over the years


> For the **'Year borrower\'s rate vs. LoanOriginalAmount vs. ProsperRatin> For the **'Year borrower\'s rate vs. LoanOriginalAmount vs. ProsperRating'**

>> The are about 30000 Loans issued before 2009

>> The ProsperRate with the **highest counts** in most years after 2009 is **B** then **c**

>> on the years 2011 and 2012, most Loans are of **ProsperRate (AA)**

>> The loans with the **lowest Value** on all years are of  **ProsperRate (HR)**, except for **year 2009**

>> om year 2009, the **ProsperRate (E)** has the **lowest value**


> For the **'Year borrower\'s rate vs. LoanOriginalAmount vs. EmploymentStatus'**

>> The are about 9000 Loans issued before 2009

>> The EmploymentStatus with the **highest value** in most years after 2009 is **Employed**

>> on the year 2007, most Borrowers were **Self-Employed**

>> on the year 2009, most Borrowers were of **other catigories**

>> The borrower with the lowest loan values most of the years were **Not-Employed** 

>> there were years when the **Not-Employed** the didn't take any loans like: 2007-2008-2009-2014-2013

> For the **'Year borrower\'s rate vs. BorrowerAPR vs. ProsperRating'**

>> The are about 0.25 Loans issued before 2009

>> over the years, the values of **BorrowerAPR** of all **ProsperRating** are almost the same
and they hold the ae ranking excpt for year 2009

>> In all years from 2010 to 2014, the **ProsperRating** from **highest to lowest** was

>>> **HR, E, D, C, B, A then AA**

>> on the year 2009, the **ProsperRating** from **highest to lowest** was 

>>> E, HR, D, C, Not Rated, B, A then AA**


> For the **'Year borrower\'s rate vs. BorrowerAPR vs. ProsperRating'**

>> The are about 0.25 Loans issued before 2009

>> over the years, the values of **BorrowerAPR** of all **ProsperRating** are almost the same
and they hold the ae ranking excpt for year 2009

>> In all years from 2010 to 2014, the **ProsperRating** from **highest to lowest** was

>>> **HR, E, D, C, B, A then AA**

>> on the year 2009, the **ProsperRating** from **highest to lowest** was 

>>> E, HR, D, C, Not Rated, B, A then AA**


> For the **'Year borrower\'s rate vs. BorrowerAPR vs. EmploymentStatus'**

>> The are about 0.25 Loans issued before 2007

>> on the years 2007 and 2014, the results are almost identicals

>> on the years 2008 and 2013, the results are almost identicals

>> on the years 2009 and 2012, the results are almost identicals

>> on the years 2010 and 2011, the results are almost identicals

>> The **Employed** catigory had the **highest BorrowAPR** only on 2009

>> The **Not-Employed** catigory had the **highest BorrowAPR** only on 2013

>> The **Self-Employed** catigory had the **highest BorrowAPR** only on 2011 and 2012

>> The **other catigories** catigory had the **highest BorrowAPR** only on 2010 and 2014

>> The **Full-Time** catigory had the **lowest BorrowAPR** over the years except for 2007-2008

>> on the years 2007 and 2008, the **lowest BorrowAPR** are **Part-Time and other** catigories


## Key Insights for Presentation

> For the presentation, I used the same as the exproration plots.
> I excluded only the violin, point and box plots from the **Bivariant section**, 
as I already discussed them again with more important analysis in the **mulivariant Section**  
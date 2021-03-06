# What is the Data Science?
[Data Science Venn Diagram v2.0](http://www.anlytcs.com/2014/01/data-science-venn-diagram-v20.html)

To help you understand what modeling process is, here's a simplified step-by-step breakdown of how to create a predictive model.

1. Formulate the problem
2. Clean your data
3. Identify features or `Feature Engineering`
4. Select algorithm
5. Create and validate your model
6. Generate insights and data visualization

## Part I - Formulate the problem by asking the `right` questions
The first step in `Machine Learning (ML)` is to decide what you want to predict, which is known as the `lable` or `target answer`. Investing time in deciding which target makes most sense for you to predict will save you from building models that don't answer your question.

## Part II - Clean Your Data
Remove inaccurate or irrelevant information from your dataset. Incorrect data can lead to false conclusions when you're modeling.

## A Few Commandments of Data Validation 
* Data Validation is not the same as Verification. Data validation is mandated by FDA regulation.

### Example: how to validate precise result of 2 powered to 1009 obtained from unknown source:
```
2**1009 = 5486124068793688683255936251187209270074392635932332070112001988456197381759672947165175699536362793613284725337872111744958183862744647903224103718245670299614498700719996264535590197791934024641512541262359795191593953928908168990292758500391456212260452596575509589842140073806143686060649302051520512
```

### Reproducibility from SAS Enterprise Guide 6.1  

```SAS
   proc groovy;
       submit;
           import java.math.BigInteger

           def x = BigInteger.valueOf(2).pow(BigInteger.valueOf(1009).intValue())
           def y = x.toString()
           def l = y.length()
           println "2 ** 1009 is " + y
           println "length of digit = " + l
       endsubmit;
  Run;
  
  
  2**1009 is 5486124068793688683255936251187209270074392635932332070112001988456197381759672947165175699536362793613284725337872111744958183862744647903224103718245670299614498700710006264535590197791934024641512541262359795191593953928908168990292758500391456212260452596575509589842140073806143686060649302051520512
  
  length of digit = 304
```

### Cross-validation using SAS Viya Python Jupyter Notebook (SAS Cloud Analytics Python 3.5.2)

```
  2**1009 = 5486124068793688683255936251187209270074392635932332070112001988456197381759672947165175699536362793613284725337872111744958183862744647903224103718245670299614498700710006264535590197791934024641512541262359795191593953928908168990292758500391456212260452596575509589842140073806143686060649302051520512
```
* Skill disparity and bias of person who conducts data validation play significant role in drawing conclusion.

### Example: What do you expect the result?

```SAS
   data _null_;
       do i = 1 to 10;
           x + 0.1;
       end;
       if x = 1 then 
           put 'x is equal to 1';
       else
           put 'x is not equal to 1';
   run;
```
* `False Positive` and `False Negative` result from validation may lead to loss of reputation or revenue. Positive result means that according to the test, the patient has the disease. A Negative result means the test concludes that the patient doesn't have the disease. Therefore, False Positive implies defect does not exist in reality but your test result from experiment design or methodology concludes Positive or capture it whereas False Negative implies defect does exist in reality but your test result from experiment design or methodology concludes Negative or cannot capture it.

* No `Gold Standard` for validation has yet emerged


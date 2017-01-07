## 10 Commandments of Data Validation
1. Data Validation means different thing to diffrent people
   ### Example
   ```
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

2. Skill disparity and bias of people who conducts data validation plays significant role in data validation
### Example
3. False Positive and Negative result from validation may lead to loss of reputation or revenue
### Example

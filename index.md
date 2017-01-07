##A Few Commandments of Data Validation after data is generated from SAS code
1. Data Validation means different thing to diffrent people
   ###Example: how to validate result of 2 powered to 1009 after running SAS code
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
  ```
2. Skill disparity and bias of people who conducts data validation plays significant role in data validation
   ###Example
   ```SAS
   ```
3. False Positive and Negative result from validation may lead to loss of reputation or revenue
   ###Example
   ```SAS
   ```

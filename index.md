##A Few Commandments of Data Validation after data is generated from SAS code
1. Data Validation is not the same as Verification
   ###Example: how to validate result of 2 powered to 1009 obtained from unidentified source:
   ```
2**1009 = 5486124068793688683255936251187209270074392635932332070112001988456197381759672947165175699536362793613284725337872111744958183862744647903224103718245670299614498700719996264535590197791934024641512541262359795191593953928908168990292758500391456212260452596575509589842140073806143686060649302051520512
```
   ###Answer  
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
2. Skill disparity and bias of person who conducts data validation plays significant role in drawing conclusion

   ###Example
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
3. False Positive and Negative result from validation may lead to loss of reputation or revenue
  

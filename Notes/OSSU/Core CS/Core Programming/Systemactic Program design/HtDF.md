****
[[How to design functions Recipe]]
The [(HtDF)](https://courses.edx.org/courses/course-v1:UBCx+SPD1x+2T2015/77860a93562d40bda45e452ea064998b/?_gl=1*yk6g87*_gcl_au*MzY3NTM0NDQ3LjE3NDA4ODU0Nzk.*_ga*MTEyMTM3MjMwNC4xNzQwODg1NDc5*_ga_D3KS4KMDT0*MTc0MTExNjYxNi4yLjEuMTc0MTExNjY3MS41LjAuMA..#HtDF) recipe consists of the following steps:

1. [Signature, purpose and stub.](https://courses.edx.org/courses/course-v1:UBCx+SPD1x+2T2015/77860a93562d40bda45e452ea064998b/?_gl=1*yk6g87*_gcl_au*MzY3NTM0NDQ3LjE3NDA4ODU0Nzk.*_ga*MTEyMTM3MjMwNC4xNzQwODg1NDc5*_ga_D3KS4KMDT0*MTc0MTExNjYxNi4yLjEuMTc0MTExNjY3MS41LjAuMA..#S1)
2. [Define examples, wrap each in check-expect.](https://courses.edx.org/courses/course-v1:UBCx+SPD1x+2T2015/77860a93562d40bda45e452ea064998b/?_gl=1*yk6g87*_gcl_au*MzY3NTM0NDQ3LjE3NDA4ODU0Nzk.*_ga*MTEyMTM3MjMwNC4xNzQwODg1NDc5*_ga_D3KS4KMDT0*MTc0MTExNjYxNi4yLjEuMTc0MTExNjY3MS41LjAuMA..#S2)
3. [Template and inventory.](https://courses.edx.org/courses/course-v1:UBCx+SPD1x+2T2015/77860a93562d40bda45e452ea064998b/?_gl=1*yk6g87*_gcl_au*MzY3NTM0NDQ3LjE3NDA4ODU0Nzk.*_ga*MTEyMTM3MjMwNC4xNzQwODg1NDc5*_ga_D3KS4KMDT0*MTc0MTExNjYxNi4yLjEuMTc0MTExNjY3MS41LjAuMA..#S3)
4. [Code the function body.](https://courses.edx.org/courses/course-v1:UBCx+SPD1x+2T2015/77860a93562d40bda45e452ea064998b/?_gl=1*yk6g87*_gcl_au*MzY3NTM0NDQ3LjE3NDA4ODU0Nzk.*_ga*MTEyMTM3MjMwNC4xNzQwODg1NDc5*_ga_D3KS4KMDT0*MTc0MTExNjYxNi4yLjEuMTc0MTExNjY3MS41LjAuMA..#S4)
5. [Test and debug until correct](https://courses.edx.org/courses/course-v1:UBCx+SPD1x+2T2015/77860a93562d40bda45e452ea064998b/?_gl=1*yk6g87*_gcl_au*MzY3NTM0NDQ3LjE3NDA4ODU0Nzk.*_ga*MTEyMTM3MjMwNC4xNzQwODg1NDc5*_ga_D3KS4KMDT0*MTc0MTExNjYxNi4yLjEuMTc0MTExNjY3MS41LjAuMA..#S5)   


### question:

![Question](https://github.com/ssahu200122/Obsidian-vault/blob/main/Notes/resources/q.png?raw=true)

```
;; String -> String                        ;Signature
;; append s to a string                    ;Purpose

(check-expect (plural "Apple")"Apples")    ;Examples
(check-expect (plural "Ball")"Balls")

;(define (plural s) "")                    ;Stub

;(define (plural s)                        ;Template
;    (...s))

(define (plural s)                         ;coded body of the function
    (string-append s "s"))



```

## Note: 

- ### Signature of the function should be most specific type possible

	***Example:***   a function Image -> Number produce area = height * width pixel^2
          ,can we more specific Image -> Integer
- ### Purpose of the function should tell more about function then Signature
- ### A function should have sufficient number of tests

    ***Example:***  A Boolean function should have at least two tests
 
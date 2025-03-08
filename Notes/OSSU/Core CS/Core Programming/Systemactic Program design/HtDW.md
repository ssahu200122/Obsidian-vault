[[How to design world]]




World program design is divided into two phases, each of which has sub-parts:

###  Domain analysis (use a piece of paper!)
1. Sketch program scenarios
2. Identify constant information
3. Identify changing information
4. Identify big-bang options
###### Big bang options:

| If your program needs to:              | Then it needs this option: |
| -------------------------------------- | -------------------------- |
| change as time goes by (nearly all do) | on-tick                    |
| display something (nearly all do)      | o-draw                     |
| change in response to key presses      | on-key                     |
| change in response to mouse activity   | on-mouse                   |
| stop automatically                     | stop-when                  |

### Build the actual program
1. Constants (based on 1.2 above)
2. Data definitions using [HtDD](https://courses.edx.org/courses/course-v1:UBCx+SPD1x+2T2015/77860a93562d40bda45e452ea064998b/?_gl=1*7trowx*_gcl_au*MzY3NTM0NDQ3LjE3NDA4ODU0Nzk.*_ga*MTEyMTM3MjMwNC4xNzQwODg1NDc5*_ga_D3KS4KMDT0*MTc0MTM0OTY4OS42LjEuMTc0MTM0OTc1Mi41Ny4wLjA.#HtDD) (based on 1.3 above)
3. Functions using [HtDF](https://courses.edx.org/courses/course-v1:UBCx+SPD1x+2T2015/77860a93562d40bda45e452ea064998b/?_gl=1*7trowx*_gcl_au*MzY3NTM0NDQ3LjE3NDA4ODU0Nzk.*_ga*MTEyMTM3MjMwNC4xNzQwODg1NDc5*_ga_D3KS4KMDT0*MTc0MTM0OTY4OS42LjEuMTc0MTM0OTc1Mi41Ny4wLjA.#HtDF)
4. main first (based on 1.3, 1.4 and 2.2 above)
5. wish list entriesfor big-bang handlers

6. Work through wish list until done


> [!question] 
> #question
> ![[Pasted image 20250308113359.png]] 
## Domain analysis: 

![[Notes/OSSU/Core CS/Core Programming/systemactic Program design/How to design world.md#^group=dtCfPt_MBx9qpQzfh2SQj|1000]]

| Constant info | Changing info | Big Bang Options |
| ------------- | ------------- | ---------------- |
| w             | CAT-X         | on-tick          |
| h             |               | on-draw          |
| CTR-Y         |               |                  |
| cat_image     |               |                  |
| MTS           |               |                  |


> [!info]- World program template
> ```
> (require 2htdp/image)
> (require 2htdp/universe)
> 
> ;; My world program  (make this more specific)
> 
> ;; =================
> ;; Constants:
> 
> 
> ;; =================
> ;; Data definitions:
> 
> ;; WS is ... (give WS a better name)
> 
> 
> 
> ;; =================
> ;; Functions:
> 
> ;; WS -> WS
> ;; start the world with ...
> ;; 
> (define (main ws)
>   (big-bang ws                   ; WS
>             (on-tick   tock)     ; WS -> WS
>             (to-draw   render)   ; WS -> Image
>             (stop-when ...)      ; WS -> Boolean
>             (on-mouse  ...)      ; WS Integer Integer MouseEvent -> WS
>             (on-key    ...)))    ; WS KeyEvent -> WS
> 
> ;; WS -> WS
> ;; produce the next ...
> ;; !!!
> (define (tock ws) ...)
> 
> 
> ;; WS -> Image
> ;; render ... 
> ;; !!!
> (define (render ws) ...)
> ```

```
(require 2htdp/image)
(require 2htdp/universe)

;; A Program in which a cat walks from left to right acroos the screen

;; =================
;; Constants:


;; =================
;; Data definitions:

;; WS is ... (give WS a better name)



;; =================
;; Functions:

;; WS -> WS
;; start the world with ...
;; 
(define (main ws)
  (big-bang ws                   ; WS
            (on-tick   tock)     ; WS -> WS
            (to-draw   render)   ; WS -> Image
            (stop-when ...)      ; WS -> Boolean
            (on-mouse  ...)      ; WS Integer Integer MouseEvent -> WS
            (on-key    ...)))    ; WS KeyEvent -> WS

;; WS -> WS
;; produce the next ...
;; !!!
(define (tock ws) ...)


;; WS -> Image
;; render ... 
;; !!!
(define (render ws) ...)
```
Compound data is used to bind together the data of similar types
**Example** : (x, y) coordinates etc.

```
(define-struct pos ( x y))           ;Definition

(define P1 (make-pos 2 3))           ;Constructor

P1              ;(make-pos 2 3)      ;Calling

(pos-x P1)      ;2                   ;Selector
(pos-y P1)      ;3

(pos? P1)       ;true                ;Predicate
(pos? "Hello")  ;false
```


## How to form compound data definitions using the HtDD recipe:

```
(define-struct player (firstName secondName))
;; Player is (make-player String String)
;; interp. (make-player firstName secondName) is a hockey player with
;;          - firstName is the first name of the hockey player
;;          - secondName is the last name of the hockey player

(define P1 (make-player "Sourabh" "Sahu"))             ;Example

#; 
(define (fn-for-player p))
 
```

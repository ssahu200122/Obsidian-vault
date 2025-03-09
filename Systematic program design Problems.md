

# Compound data:

### Movie ticket

> [!question]- 
#question
> Data Definition
> ![[Pasted image 20250309124706.png]]
>> [!done]- Solution
>> ```
>> (define-struct movie (title budget year))
>> ;; Movie is (make-movie String Natural Natural)
>> ;; interp. (make-movie title budget year) is a movie with
>> ;;          - title is movie name
>> ;;          - budget is movie budget in INR (crore)
>> ;;          - year is the movie release year
>> 
>> (define M1 (make-movie "RRR" 550 2022))
>> (define M2 (make-movie "Pushpa 2: The Rule" 500 2024))
>> 
>> #;
>> (define (fn-for-movie m)
>>   (... (movie-title m)      ;String
>>        (movie-budget m)     ;Natural
>>        (movie-year m)       ;Natural
>>   )
>> )
>> 
>> ;; Template rules used:
>> ;;       -Compound: 3 fields
>> 
>> ```

> [!question]- 
#question
![[Pasted image 20250309130551.png]]
> Funtion:
>> [!done]- Solution
>> ```
>> ;; Movie Movie -> String
>> ;; Produces the title of the most recently released movie
>> 
>> (check-expect (most-recent M1 M2) (movie-title M2))
>> 
>> ;(define (most-recent m1 m2)" ")
>> 
>> #;
>> (define (fn-for-movie m1 m2)
>>   (... (movie-title m1)      ;String
>>        (movie-title m2)      ;String
>>        (movie-budget m1)     ;Natural
>>        (movie-budget m2)     ;Natural
>>        (movie-year m1)       ;Natural
>>        (movie-year m2)       ;Natural
>>   )
>> )
>> 
>> (define (most-recent m1 m2)
>>   (if (>= (movie-year m1) (movie-year m2))
>>       (movie-title m1)
>>       (movie-title m2)
>>   )
>> )
>> 
>> 
>> ```

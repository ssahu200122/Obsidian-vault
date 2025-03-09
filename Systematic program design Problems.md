

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

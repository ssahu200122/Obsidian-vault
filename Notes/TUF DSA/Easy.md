# Largest Element  in an Array

- [ ] Overall Done
  - [ ] [Article](https://takeuforward.org/data-structure/find-the-largest-element-in-an-array/)
  - [ ] [Youtube](https://youtu.be/37E9ckMDdTk)
  - [ ] [Practice](https://bit.ly/3Pld280)
  - [ ] Note
  - [ ] Revision

### Array 
array is the data structure which contains similar type of data

- ==max size== that can be defined in main function  = 10^6
- ==max size== that can be defined in global scope  = 10^7

> [!abstract]+ Code
> Code:
>```
> #include<bits/stdc++.h>
> using namespace std;
> int A[6];
> int main(){
>     int B[6];
>     for(int i=0;i<6;i++){
>         cout<<A[i]<<" ";
>     }
>     cout<<endl;
>     for(int i=0;i<6;i++){
>         cout<<B[i]<<" ";
>     }
>     return 0;
> }
> ```
> OUTPUT:
> ```OUTPUT:
> 0 0 0 0 0 0 
> 2005199424 1586769954 -2 6422280 2005175325 4201040
> ```

- In above example there are two Arrays A and B. when a Array is declared in global scope then, it initialized by 0 otherwise by garbage value


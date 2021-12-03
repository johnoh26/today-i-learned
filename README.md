# Today-I-Learned
Goal: record my progress as a developer, an investor and a person


------------------------------ 2022 ------------------------------

Goals for the year
1) Re-complete Leetcode Explore + bit manipulation + top interview questions
2) Start a side project that can scale to practice implementing system design concepts (DNS, CDN, cache, load balancer, DB replicas, sharding, hashing, service workers, etc.)

------------------------------ 2021 ------------------------------

Goals for the year
1) Finish Leetcode Explore
2) Finish reading Donne Martin's system design primer


12/2
- in javascript, we can use filter to mimic map and vice versa, although the result will be [2,4,6,8,10] vs [undefined, 2, undefined, 4, undefined, 6, undefined, 8, undefined, 10] when we filter even numbers from [1,2,3,4,5,6,7,8,9,10] using filter vs. map.
- can't use filter and/or map to replicate reduce without creating another variable, because the function's signature is different i.e. map and filter return an array but reduce returns a single value
- Javascript has interesting type coersion and conversion system.
- 6 primitive types in JS: number, boolean, null, undefined, string, symbol and 1 complex type: object
- in JS, things are truthy or falsey, but truthy is not equal to true. Truthy means can be coerced to being true.
- falsey things are empty string ("" or ''), 0 (-0 and 0n), null, undefined and NaN, and the rest are truthy

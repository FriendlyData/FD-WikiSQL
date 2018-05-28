Metadata matching approach applied to the WikiSQL question corpus. 

Input: table with columns, their types and data, as well as a set of questions that the table contains answer to.

Output: query object that can be unambiguously transformed into SQL

Method: since we have both columns and data, let's try to match those in the question and see if it's enough to generate the object. The results are in the attached files. In the question strings, columns are marked with [ ], data values with { }.

Full comparison, aggregation not taken into account
Matched: 5924
Not matched: 3221
Precision: 64.7785675232367%

Only conditions are compared, select field is not taken into account
Conds matched: 6824
Conds not matched: 2321
Conds precision: 74.6200109349371%

Method (column & metadata matching) advantages:
- works quite well on completely unfamiliar data with random structure
- works out of the box, no manual configuration needed (though it can boost the precision)
- can be used for languages other than English
- requires no learning, hence no manual annotation (though it can help with precision)

Method limitations:
- requires relatively explicit match of the stored and queried columns and data values (at least a few letters should match)

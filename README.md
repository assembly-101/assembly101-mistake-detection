# mistake-detection

## Annotation
Each csv file corresponds to an assembly sequence within each csv file are the annotations. 
- There are in total 328 sequences. 
- Each annotation contains the 
  - **start** and **end** timestamps, followed by the 
  - **verb** (attach, detach) and the 
  - two working objects (**this, that**), the 
  - mistake **label** and the 
  - **remark** are then appened.

### Examplar

For example:
**nusar-2021_action_both_9033-c02a_9033_user_id_2021-02-04_140532.csv**

- **9033** is the actor while **c02d** is the toy id.

| start      | end      | verb     | this          | that          | label      | remark                  |
|------------|----------|----------|---------------|---------------|------------|-------------------------|
| 7257       | 7817     | attach   | interior      | chassis       | correct    |                         |
| 8419       | 8736     | detach   | interior      | chassis       | mistake    | shouldn't have happened |
| 8736       | 9138     | attach   | interior      | chassis       | correct    |                         |
| 10039      | 10355    | attach   | body          | chassis       | mistake    | wrong order             |
| 10749      | 11184    | attach   | cabin         | interior      | mistake    | previous one is mistake |
| 11184      | 11601    | interior | cabin         | interior      | correction |                         |
| 11601      | 11806    | detach   | body          | chassis       | correction |                         |
| 11806      | 11864    | attach   | cabin         | interior      | correct    |                         |
| 11864      | 12105    | attach   | body          | chassis       | correct    |                         |
| 12615      | 13443    | attach   | roof          | cabin         | correct    |                         |
| 13443      | 14098    | attach   | arm           | bucket        | correct    |                         |
| 14098      | 14147    | attach   | arm           | boom          | correct    |                         |
| 14658      | 15729    | attach   | arm connector | chassis       | mistake    | wrong order             |
| 16490      | 16848    | detach   | arm connector | chassis       | correction |                         |
| 16848      | 18532    | attach   | arm connector | boom          | mistake    | wrong position          |
| 18532      | 19342    | attach   | arm connector | chassis       | correct    |                         |
| 19342      | 19509    | detach   | arm connector | chassis       | mistake    | shouldn't have happened |
| 19509      | 19835    | detach   | arm           | boom          | correction |                         |
| 19835      | 20641    | attach   | arm connector | boom          | correct    |                         |
| 20641      | 21476    | attach   | arm connector | chassis       | correct    |                         |
| 21476      | 21059    | detach   | arm connector | chassis       | mistake    | shouldn't have happened |
| 21509      | 21527    | detach   | boom          | arm connector | mistake    | shouldn't have happened |
| 21527      | 21795    | attach   | arm connector | chassis       | correct    |                         |
| 21795      | 21830    | detach   | arm connector | chassis       | mistake    | shouldn't have happened |
| 21830      | 22234    | attach   | arm connector | boom          | correct    |                         |
| 22234      | 23444    | attach   | arm connector | chassis       | correct    |                         |
| 23444      | 24401    | attach   | arm           | boom          | correct    |                         |
| 24401      | 25738    | attach   | bumper        | body          | correct    |                         |
| 25738      | 27434    | attach   | wheel         | chassis       | correct    |                         |

- **wrong order**: meaning the action is a mistake in ordering
- **previous one is mistake**: meaning this action is also a ordering mistake but caused by preceding ordering mistakes in context
- **shouldn't have happened**: meaning this action is uncessary detach of parts
- **wrong position**: meaning the two parts are not attached in the right position


There is no *correction* for the *shouldn't have happened* type of mistake.



## License
Assembly101 is licensed by us under the Creative Commons Attribution-NonCommerial 4.0 International License, found [here](https://creativecommons.org/licenses/by-nc/4.0/). The terms are :
- **Attribution** : You must give appropriate credit, provide a link to the license, and indicate if changes were made. You may do so in any reasonable manner, but not in any way that suggests the licensor endorses you or your use.
- **NonCommercial** : You may not use the material for commercial purposes.

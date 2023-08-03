# assembly101-mistake-detection
This repository contains annotations for the Mistake Detection benchmark of Assembly101. Please refer to [Every Mistake Counts in Assembly](https://arxiv.org/abs/2307.16453) for further details regarding annotations and baselines.

If you find these annotations helpful and use them in your research, kindly cite the following:
```
@article{sener2022assembly101,
    title = {Assembly101: A Large-Scale Multi-View Video Dataset for Understanding Procedural Activities},
    author = {F. Sener and D. Chatterjee and D. Shelepov and K. He and D. Singhania and R. Wang and A. Yao},
    journal = {CVPR 2022},
}

@article{ding2023every,
  title={Every Mistake Counts in Assembly},
  author={Ding, Guodong and Sener, Fadime and Ma, Shugao and Yao, Angela},
  journal={arXiv preprint arXiv:2307.16453},
  year={2023}
}
```

## File structure
Each .csv file provides the mistake annotation for an assembly sequence.
- There are 328 sequences in total.
- Each annotation contains:
  - `start` and `end` timestamps
  - `verb` (attach, detach) 
  - two working objects (`this`, `that`) 
  - mistake `label`
  - `remark` (if any)

## Example Annotation

For the assembly sequence `nusar-2021_action_both_9033-c02a_9033_user_id_2021-02-04_140532.csv`

- `9033` is the actor while `c02a` is the toy id.
- `wrong order` : this action is an ordering mistake
- `previous one is mistake` : this action is also an ordering mistake but is caused by the preceding ordering mistakes in the context
- `shouldn't have happened` : this detach action is unnecessary
- `wrong position` : the two parts are not attached at their correct position

<br/>

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


**Note**: There is no *correction* for the *shouldn't have happened* type of mistake.


## License
Assembly101 is licensed by us under the Creative Commons Attribution-NonCommerial 4.0 International License, found [here](https://creativecommons.org/licenses/by-nc/4.0/). The terms are :
- **Attribution** : You must give appropriate credit, provide a link to the license, and indicate if changes were made. You may do so in any reasonable manner, but not in any way that suggests the licensor endorses you or your use.
- **NonCommercial** : You may not use the material for commercial purposes.

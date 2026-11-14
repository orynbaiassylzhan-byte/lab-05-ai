# Lab 05 Conclusion

## 1. Workflow and agent

On the 15 fixed-shape questions, the workflow answered 13 correctly, compared with 9 for the bare agent. It used 3,852 tokens and 15 model calls, while the agent used 19,835 tokens and 26 calls. The workflow therefore used about 5.15 times fewer tokens. Both failed on q21 and q22 because the tools rejected the region aliases. The agent was more flexible: it answered 7 of the 9 open questions correctly, which this workflow could not attempt.

## 2. Harness layers

Layer 1 increased correct answers from 16/24 to 18/24 by recovering from tool errors on q23 and q24. Layer 2 alone did not change the outcomes or token usage, although its repeated-call protection activated under Layer 3 in the q18 trace. Layer 3 reduced wrong answers from 6 to 4 by turning q18 and q22 into no answer, without increasing correct answers.

Question q08 remained wrong because the model selected Jambyl incorrectly for the lowest-wage question. The harness corrected the missing ANSWER line but accepted the region name because it appeared in the tool output. This shows that grounding confirms support from a tool, not that the model selected the correct answer.

## 3. Notes

The notes fixed q21 and q22, but overall correct answers decreased from 18/24 to 15/24. Questions q04, q14, q15, and q16 changed from correct to no answer, while q07 changed from correct to wrong. Token usage increased from 60,116 to 74,116, about 23.3%, while model calls remained at 74. Runtime increased from 111.3 to 132.3 seconds. In this experiment, the notes helped with aliases but increased cost and reduced overall accuracy. Additional instructions need testing because they can improve some answers while making others worse.

# Rouge Implementation for Korean
original source code from https://github.com/google-research/google-research/tree/master/rouge

기존 rouge_scorer는 알파벳과 숫자를 제외하고는 제거했기 때문에, tokenize.py 에서 해당 부분을 주석처리했습니다.

<!-- ```
pip install korouge_score
``` -->

```python
from korouge_score import rouge_scorer

scorer = rouge_scorer.RougeScorer(["rouge1", "rouge2", "rougeL", "rougeLsum"])

ref = "안녕하세요 반가워요 오늘 뭐 먹을래요?"
pred = "안녕 ㅋ 반가워 오늘 뭐 할래?"

print(scorer.score(ref, pred))
>>> {'rouge1': Score(precision=0.3333333333333333, recall=0.4, fmeasure=0.3636363636363636), 'rouge2': Score(precision=0.2, recall=0.25, fmeasure=0.22222222222222224), 'rougeL': Score(precision=0.3333333333333333, recall=0.4, fmeasure=0.3636363636363636), 'rougeLsum': Score(precision=0.3333333333333333, recall=0.4, fmeasure=0.3636363636363636)}
```

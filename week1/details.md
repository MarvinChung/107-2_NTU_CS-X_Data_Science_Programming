full code is available at https://github.com/MarvinChung/Political-News-Analysis
```
# old code
# 可能人名
possible_name = first_n_words(cutted_dict, 1000, 3, 3)
possible_name[:10]
```
output:

![Imgur](https://i.imgur.com/YCDWmYC.png)

modify to 
```
# 可能人名
possible_name = []
candidate_name = first_n_words(cutted_dict, 1000, 3, 3)
import jieba.posseg as psg
for word, cts in candidate_name:
    for x in psg.cut(word):
        if(x.flag == 'nrfg' or x.flag == 'nr'):
            possible_name.append((word, cts))
possible_name[:10]
```
![Imgur](https://i.imgur.com/hKkAZRQ.png)

pros: using jieba POS tagging getting more precision people name.
cons: some names are lost


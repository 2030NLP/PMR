# PMR
## Introduction
Premise-based Multi-modal Reasoning(PMR) is a task that explores the ability of models to reason with both textual (from the premise) and visual(from images) clues.

Through manually annotation and adversarial generation, we create PMR dataset with 32,720 samples. Here are the stats for PMR, and you can explore it on our [website](https://2030nlp.github.io/PMR).

<table class="tg">
<thead>
  <tr>
    <th class="tg-0pky"></th>
    <th class="tg-0pky" colspan="3"><span style="font-weight:bold">Ori.</span></th>
    <th class="tg-0pky" colspan="3"><span style="font-weight:bold">Adv.</span></th>
    <th class="tg-0pky">Total~</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"><span style="font-weight:bold">Train</span></td>
    <td class="tg-0pky"><span style="font-weight:bold">Val</span></td>
    <td class="tg-0pky"><span style="font-weight:bold">Test</span></td>
    <td class="tg-0pky"><span style="font-weight:bold">Train</span></td>
    <td class="tg-0pky"><span style="font-weight:bold">Val</span></td>
    <td class="tg-0pky"><span style="font-weight:bold">Test</span></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">\#samples</td>
    <td class="tg-0pky">12,080</td>
    <td class="tg-0pky">1,538</td>
    <td class="tg-0pky">1,742</td>
    <td class="tg-0pky">12,080</td>
    <td class="tg-0pky">1,538</td>
    <td class="tg-0pky">1,742</td>
    <td class="tg-0pky">30,720</td>
  </tr>
  <tr>
    <td class="tg-0pky">\#unique 1-gram</td>
    <td class="tg-0pky">9,882</td>
    <td class="tg-0pky">3,819</td>
    <td class="tg-0pky">4,101</td>
    <td class="tg-0pky">8,046</td>
    <td class="tg-0pky">3,071</td>
    <td class="tg-0pky">3,359</td>
    <td class="tg-0pky">11,041</td>
  </tr>
  <tr>
    <td class="tg-0pky">\#unique 2-gram</td>
    <td class="tg-0pky">72,048</td>
    <td class="tg-0pky">17,678</td>
    <td class="tg-0pky">19,292</td>
    <td class="tg-0pky">50,526</td>
    <td class="tg-0pky">12,236</td>
    <td class="tg-0pky">13,453</td>
    <td class="tg-0pky">84,365</td>
  </tr>
  <tr>
    <td class="tg-0pky">Avg premise length</td>
    <td class="tg-0pky">9.48</td>
    <td class="tg-0pky">9.47</td>
    <td class="tg-0pky">9.54</td>
    <td class="tg-0pky">9.48</td>
    <td class="tg-0pky">9.47</td>
    <td class="tg-0pky">9.54</td>
    <td class="tg-0pky">9.49</td>
  </tr>
  <tr>
    <td class="tg-0pky">Avg action text length</td>
    <td class="tg-0pky">14.38</td>
    <td class="tg-0pky">14.41</td>
    <td class="tg-0pky">14.45</td>
    <td class="tg-0pky">14.20</td>
    <td class="tg-0pky">14.42</td>
    <td class="tg-0pky">14.31</td>
    <td class="tg-0pky">14.31</td>
  </tr>
  <tr>
    <td class="tg-0pky">Avg \#objects mentioned</td>
    <td class="tg-0pky">1.92</td>
    <td class="tg-0pky">1.91</td>
    <td class="tg-0pky">1.94</td>
    <td class="tg-0pky">2.42</td>
    <td class="tg-0pky">2.43</td>
    <td class="tg-0pky">2.38</td>
    <td class="tg-0pky">2.17</td>
  </tr>
  <tr>
    <td class="tg-0pky">\#images</td>
    <td class="tg-0pky">9,536</td>
    <td class="tg-0pky">1,213</td>
    <td class="tg-0pky">1,370</td>
    <td class="tg-0pky">9,536</td>
    <td class="tg-0pky">1,213</td>
    <td class="tg-0pky">1,370</td>
    <td class="tg-0pky">12,119</td>
  </tr>
  <tr>
    <td class="tg-0pky">\#movies covered</td>
    <td class="tg-0pky">1,353</td>
    <td class="tg-0pky">209</td>
    <td class="tg-0pky">170</td>
    <td class="tg-0pky">1,353</td>
    <td class="tg-0pky">209</td>
    <td class="tg-0pky">170</td>
    <td class="tg-0pky">1,732</td>
  </tr>
</tbody>
</table>

## Dataset Access
Dataset can be downloaded at [Google Drive](https://drive.google.com/drive/folders/15IZny7KKz4RRwd9c9D1ob3Bi3orsqQMe?usp=sharing).

PMR has been selected as one of the evalution tasks on CCL2022, and we provide full train and validation sets(both original and adversarial samples) to train models. For model evalution, you can submit the predictions of model on test set(`test-ori-without-label.jsonl`) by mailing at corlder@outlook.com, and we will give feedback timely.

### Data Format
Here is a brief introduction to the data format.
```
{
        "total_id": 98,
        # Name of movie which the image is from.
	"movie": "3051_NANNY_MCPHEE_RETURNS",
  
	# Object tags from Fast RCNN
	"objects": ["person", "person", "handbag", "spoon"],
  
	# Path of the image
	"img_fn": "lsmdc_3051_NANNY_MCPHEE_RETURNS/3051_NANNY_MCPHEE_RETURNS_01.19.27.912-01.19.30.662@0.jpg",
	
	# Id of the image
	"img_id": "train-5244",
  
	# Path of the file storing the information of bounding boxes
	"metadata_fn": "lsmdc_3051_NANNY_MCPHEE_RETURNS/3051_NANNY_MCPHEE_RETURNS_01.19.27.912-01.19.30.662@0.json",
  
	# Tokenized premise, the integers in lists indicate the index of objects in the above list.
	"premise": [[1], "and", [0], "are", "in", "good", "relationship", "."],
  
	# Category of the premise.
	"category": "character"
  
	# Tokenized actions, the intergers in lists indicate the index of objects.
	"answer_choices": [
		[[1], "with", "a", "handbag", "will", "hug", [0], "tightly", "."],
		[[1], "with", "a", "green", "handbag", "will", "shout", "at", [0], "in", "the", "kitchen", "."],
		[[1], "with", "a", "handbag", "will", "shout", "at", [0], "in", "the", "kitchen", "."],
		[[1], "with", "a", "green", "handbag", "will", "hug", [0], "tightly", "."]
		],
    
	# The types of answers in the order corresponding to the answer_choices
	"answer_types": ["Action-True", "Distractor2", "Action-False", "Distractor1"],
  
	# The index of the correct answer in answer_choices.
	"answer_label": 0
	
	# For original set, the total_id of the sample that has the same image as the current sample if it exists.(-1 is the default)
	"pal_id":-1
	
	# For adversarial set, the list of total_id which the four choices are from.
	"answer_ori_ids":[14097, 12681, 387, 13170]
}
```
### Baseline Models
We provide baseline models here. They are adapted from three vision-language pretrained models which have great performance on multimodal understanding tasks.
1. [VL-BERT](https://github.com/jackroos/VL-BERT)
2. [UNITER](https://github.com/ChenRocks/UNITER)
3. [ERINIE](https://github.com/paddlepaddle/ernie/tree/repro/ernie-vil)
### Citation
Please consider citing this paper if you find this repository useful:
```
@article{PMR2022,
	title	= {Premise-based Multimodal Reasoning: {A} Human-like Cognitive Process},
	author  = {Qingxiu Dong and
               Ziwei Qin and
               Heming Xia and
               Tian Feng and
               Shoujie Tong and
               Haoran Meng and
               Lin Xu and
               Tianyu Liu and
               Zuifang Sui and
               Weidong Zhan and
               Sujian Li and
               Zhongyu Wei},
	journal = {CoRR},
	volume  = {abs/2105.07122},
	year    = {2021},
}
```
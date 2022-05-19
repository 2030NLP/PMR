# PMR
### Introduction
Premise-based Multi-modal Reasoning(PMR) is a task that explores the ability of models to reason with both textual (from the premise) and visual(from images) clues.
Through manually annotation and adversarial generation, we create PMR dataset with 32,720 samples. Here are the stats for PMR, and you can explore it on our [website](https://2030nlp.github.io/PMR).
## Dataset Access
Dataset can be downloaded at [Google Drive](https://drive.google.com/drive/folders/15IZny7KKz4RRwd9c9D1ob3Bi3orsqQMe?usp=sharing).
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
We provide baseline models here. They are adapted from three Vision-Language Pretrained models which have great performance on multimodal understanding tasks.
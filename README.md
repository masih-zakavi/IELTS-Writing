## Grading IELTS Writing with BERT ##

### Introduction ###
This project explores automating IELTS Writing Task 1 and 2 grading using BERT, the powerful foundation NLP model. 
The IELTS exam is used extensively for evaluating English proficiency in academia and immigration. 
Grading is done manually, based on a detailed rubric linked [here](https://takeielts.britishcouncil.org/sites/default/files/ielts_writing_band_descriptors.pdf).
This projects tests BERT's ability to emulate the IELTS human graders.

### Dataset Description ###
The Kaggle dataset comprises responses to both IELTS tasks, graded by actual exam evaluators.
It includes essential features like Task Type, Question, Essay, and Overall Grade, with a total of 1435 entries.
While the questions aren't graded, they're essential for assessing the quality of the responses. 

### Model Overview ###
The approach leverages BERT's pre-trained capabilities, fine-tuning it for the IELTS grading criteria: 
task response, coherence, lexical resource, and grammatical range. 
The model processes concatenated question and essay pairs, following BERT's fine-tuning strategy from the original paper. 
Training involves segmenting the data, tokenization, and employing a regression strategy to predict scores.

### Training and Evaluation ###
The base BERT model weights are imported using the Hugging Face Transformers Library. 
These base weights are fine-tuned for the grading task over 10 epochs, with a linear warmup schedule to avoid any loss of language understanding from the base model.

### Results ###
The fine-tuned models achieve promising accuracy, with about 90% of predictions within one point of human grades for both tasks.
A discussion section is included at the end considering ways to enhance the model.

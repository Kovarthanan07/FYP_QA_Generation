# FYP_QA_Generation

# Automatic MCQ Generator

This project focuses on generating Multiple Choice Questions (MCQs) automatically from a given paragraph using Natural Language Processing (NLP) techniques. The pipeline includes summarization, answer extraction, question generation, and distractor creation, ensuring high-quality and challenging MCQs.

## Features
- **Summarization Model:** Summarizes paragraphs to a fixed range of words for consistency in question generation.
- **Answer Extraction Model:** Identifies key informative sentences based on named entities and extracts accurate answers.
- **Question Generation Model:** Generates questions by fine-tuning `GPT-Neo` and `T5` models with the SQuAD dataset.
- **Distractor Generation Model:** Creates plausible yet incorrect distractors using `Sense2Vec`.

## MCQ Generation Process
1. **Paragraph Summarization:**
   - Uses the `t5-base` model to summarize the input paragraph into 75–150 words.
   
2. **Answer Extraction:**
   - Extracts important keywords from the original and summarized paragraphs using the `MultipartiteRank` algorithm.
   - Identifies common keywords to select the final answer.

3. **Question Generation:**
   - Fine-tuned `GPT-Neo` and `T5` models take the paragraph and answer as input to generate questions.

4. **Distractor Generation:**
   - Employs `Sense2Vec` to produce high-quality distractors by leveraging word embedding techniques to generate plausible but incorrect options.

## Example
Input:  
`Barack Obama was the 44th President of the United States.`

Output:  
- Question: Who was the 44th President of the United States?  
- Correct Answer: Barack Obama  
- Distractors: George W. Bush, Bill Clinton, Donald Trump  

## Technologies Used
- Python
- NLP Models:
  - `t5-base` for summarization
  - `GPT-Neo` and `T5` fine-tuned with SQuAD dataset for question generation
  - `Sense2Vec` for distractor generation
- `MultipartiteRank` for answer extraction

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/automatic-mcq-generator.git

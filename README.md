# TEXT2SQL
The following repo contains files to Finetune and Evaluate an LLM for Text to SQL tasks.
We see a 2x improvement in ROGUE-1 and ROGUE-L scores and a 3x improvement in ROGUE-2 scores from fine-tuning. These big ROGUE performance improvements demonstrate the value of fine-tuning (see figure below).

![screenshot.png](https://github.com/jai-llm/TEXT2SQL/blob/main/ROGUE_Scores_Llama_vs_Finetune.png)
In this project we used the ROGUE score for evaluation but a better approach would be to run queries against a reference database to validate and evaluate results (WIP).

The datset used for this project is the [b-mc2/sql-create-context](https://huggingface.co/datasets/b-mc2/sql-create-context) dataset available on the Hugging Face Hub.
The model is trained using ~4K examples. Evaluation is done with ~450 test data examples that were not used during training.

The files in the repo do the following:
1. **0_Text2SQL_Create_Datav3.ipynb** (CPU) - Creates train and test datasets.
2. **1_Text2SQL_FineTune_Llama2GPTQv3.ipynb** (GPU Needed) - Finetunes LLama2GPTQ Model using training data. Takes ~20mins. 
3. **2a_Text2SQL_Evaluate_Llama2GPTQv3.ipynb** (GPU Needed) - Runs Inference on test data using the LLama2GPTQ Model. Takes ~40mins.
4. **2b_Text2SQL_Evaluate_Llama2GPTQFineTunev3.ipynb** (GPU Needed) -  Runs Inference on test data using the Finetuned LLama2GPTQ Model. Takes ~40mins.
5. **2c_Text2SQL_Compare_ROGUEv3.ipynb** (CPU) - Computes ROGUE-1, ROGUE-2, ROUGE-L Scores for both Pre & Post Finetune Models.
6. **3_Text2SQL_HFUpload_Llama2GPTQFineTunev3.ipynb** (GPU Needed) - Uploads Finetuned Model to HF Hub (WIP).

 

**Note:** Repo is work in progress with cleanup changes likely in the near future. 

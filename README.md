# TEXT2SQL
The following repo contains files to Fine-Tune and evaluate an LLM for Text to SQL tasks.
We see big improvement in ROGUE scores from fine-tuning ~100% which shows the value of fine-tuning.
ROGUE score is used for evaluation but better approach would be run queries against a database to confirm results.

The datset used for this project is the "b-mc2/sql-create-context" available on the Hugging Face Hub.
Model training uses training data. Evaluation is done with test data not used during training.

The files in the repo do the following:
1. 0_Text2SQL_Create_Datav3.ipynb (CPU) - Creates train and test datasets.
2. 1_Text2SQL_FineTune_Llama2GPTQv3.ipynb (GPU Needed) - Fine-Tunes LLama2GPTQ Model using training data. Takes about 20mins. 
3. 2a_Text2SQL_Evaluate_Llama2GPTQv3.ipynb (GPU Needed) - Runs Inference on test data using the LLama2GPTQ Model. Takes 40mins.
4. 2b_Text2SQL_Evaluate_Llama2GPTQFineTunev3.ipynb (GPU Needed) -  Runs Inference on test data using the Fine-Tuned LLama2GPTQ Model. Takes 40mins.
5. 2c_Text2SQL_Compare_ROGUEv3.ipynb (CPU) - Computes ROGUE-1, ROGUE-2, ROUGE-L Scores for both Pre & Post Fine-Tune Models.
6. 3_Text2SQL_HFUpload_Llama2GPTQFineTunev3.ipynb (GPU Needed) - Uploads Fine-Tuned Model to HF Hub.

 

**Note:** Repo is work in progress with cleanup changes likely in the next few days. 

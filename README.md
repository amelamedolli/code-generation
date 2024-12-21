# Follow the below and execute on by one.
## Clone the repo
!git clone https://github.com/towhidultonmoy/code_generation.git

## Install the libraries
!pip install  --upgrade "transformers"   "datasets"  "accelerate"  "evaluate"  "bitsandbytes"  "trl"  "peft"

!pip install aiohttp numpy tqdm pytest torch

cd ../code_generation


!mkdir tutorial


## If you want to do 20 completion for each sample for all the samples,
!python3 automodel.py --name "facebook/incoder-6B" --root-dataset humaneval --lang java --temperature 0.2 --batch-size 20 --completion-limit 20 --output-dir-prefix tutorial

cd ../evaluation/src

## Evaluate
!python3 main.py --dir ../code_generation/tutorial --output-dir ../code_generation/tutorial --recursive


cd ../


cd ../

## Get the score
!python3 pass_k.py ./tutorial/*


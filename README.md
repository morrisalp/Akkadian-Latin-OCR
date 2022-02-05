# OCR for Akkadian Latin Transliteration

This repository contains code for generating data and training OCR on Latin transliteration of ancient Akkadian texts, using the [Kraken OCR](http://kraken.re/master/index.html) framework.

## Requirements

* [Kraken](https://github.com/mittagessen/kraken) installed as follows:

Clone the Kraken Github repo and install its Conda environment from within the repo with:

`conda env create -f environment.yml`

Activating the kraken environment (`conda activate kraken`) gives access to the `kraken` and `ketos` command-line tools.

**Note:** If you want to fine-tune the model, you may want to use Kraken with CUDA (GPU acceleration). In this case you should instead install it with:

`conda env create -f environment_cuda.yml`

Note: This also creates an environment with name `kraken`. If you want both environments, edit the `.yml` file to change the environment name (e.g. to `kraken-cuda`).

## Usage Instructions

Activate the Kraken Conda environment and then run:

`kraken -i "IMAGE_FILENAME" OUTPUT_FILENAME binarize segment ocr -m MODEL_FILENAME`

Using the following values:
* IMAGE_FILENAME: Use the filename of the image you want to perform OCR on.
* OUTPUT_FILENAME: Filename of text file to write output to
* MODEL_FILENAME: Should point to the model file you want to use in `model/`

## Fine-Tuning Model

For instructions on fine-tuning the existing model on new data, see `Finetuning.md`.
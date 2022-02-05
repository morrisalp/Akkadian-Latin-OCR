# Fine-Tuning Instructions

You may fine-tune the existing model on new data. You are recommended to use GPU acceleration; see the readme for instructions on using Kraken with GPU.

Given images `image1.png`, `image2.png`, ... of Akkadian transcriptions, create a transcription HTML file with:
* `ketos transcribe --prefill model_filename -o html_filename.html image1.png image2.png ...`

Edit the transcriptions manually by opening the HTML file (and once done editing, downloading the updated HTML file by clicking "Download"), and then run this in order to generate fine-tuning training data:
* `ketos extract -o new_data_dir html_filename.html`

Now retrain the model with:
* `ketos train -i old_model_filename -o new_model_prefix new_data_dir/*.png (--resize add)`

Note: the `--resize add` allows fine-tuning to introduce new characters that were not seen during training.
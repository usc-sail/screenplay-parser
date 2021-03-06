# Robust Screenplay Parser

## Requirements

Create a conda environment and install requirements using:

```
conda create -n parser python=3.8
pip install -r requirements.txt
```

## Usage

```
Robust Movie Screenplay Parser

Usage:
    movieparser evaluate        [--data=<DATA>]
    movieparser evaluate robust [--data=<DATA>] [--results=<RESULTS>] [--names_file=<path>]
    movieparser evaluate gdi    [--data=<DATA>] [--gdi_folders=<FOLDERS>] [--ignore_scripts=<SCRIPTS>]
    movieparser create data     [--data=<DATA>] [--results=<RESULTS>] [--names_file=<path>]
    movieparser create seq      [--results=<RESULTS>] [--seqlen=<int>]
    movieparser create feats    [--results=<RESULTS>]
    movieparser train           [--results=<RESULTS>] [--seqlen=<int>] [--train_batch_size=<int>] 
                                [--eval_batch_size=<int>] [--eval_movie=<str>] [--lomo] [--learning_rate=<float>] 
                                [--enc_learning_rate=<float>] [--max_norm=<float>] [--patience=<int>] 
                                [--max_epochs=<int>] [--parallel] [--n_folds_per_gpu=<int>] [--bi] [--verbose]

Options:
    -h, --help                                      Show this help screen and exit
        --data=<DATA>                               path to data folder [default: data]
        --results=<RESULTS>                         path to results folder [default: results]
        --gdi_folders=<FOLDERS>                     comma-separated list of GDI folders 
                                                    [default: LEGO TITAN,Lionsgate,NBC Universal]
        --ignore_scripts=<SCRIPTS>                  comma-separated scripts to ignore because of annotation error
                                                    script name is GDI_folder_name/script_name e.g. LEGO TITAN/EPISODE 102
                                                    [default: ]
        --names_file=<path>                         file containing English names [default: data/names.txt]
        --seqlen=<int>                              number of sentences in a sample [default: 10]
        --train_batch_size=<int>                    training batch size [default: 256]
        --eval_batch_size=<int>                     evaluation batch size [default: 512]
        --eval_movie=<str>                          movie left out in leave-one-movie-out testing [default: all]
        --lomo                                      leave one movie out
    -l, --learning_rate=<float>                     learning rate [default: 1e-3]
        --enc_learning_rate=<float>                 learning rate of the sentence encoder [default: 1e-5]
        --max_norm=<float>                          maximum weight norm for clipping [default: 1.0]
        --patience=<int>                            maximum number of epochs to wait for dev performance to improve
                                                    [default: 5]
        --max_epochs=<int>                          maximum number of epochs [default: 5]
        --parallel                                  start training on multiple folds in lomo
        --n_folds_per_gpu=<int>                     number of simultaneous folds to train in a single gpu [default: 1]
        --bi                                        bidirectional
    -v, --verbose                                   verbose logging during training
```
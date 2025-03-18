<h1 align="center">Code for <i>Modeling Videos as Sequences of Motion Vectors</i>
</h1>
<p>
  <img alt="Version" src="https://img.shields.io/badge/version-1.1-blue.svg?cacheSeconds=2592000" />
  <a href="https://creativecommons.org/licenses/by/4.0/" target="_blank">
    <img alt="License: CC BY 4.0" src="https://img.shields.io/badge/License-CC BY 4.0-yellow.svg" />
  </a>
</p>

## Overview

This repository contains an an implementation of experiments for the paper Modeling Videos as Sequences of Motion Vectors. It consists of low level C code packaged in for GNU Linux. It could currently extract motion vectors from video encoded using h.264(AVC) and transform them into temporal and spatial sequences. 


## Getting started

```sh
Overview of directory. Names should be self-explanatory.

1. "data" contains raw, interim, and processed data
2. "src" contains all source code.
	- src/data contains code that processes transform data
	- src/utils contains utility functions (or helper functions if you would)
	- src/model contains model definition + training
3. "result" contains generated videos + metrics + visualizations


```


## Setup 

### Dependencies
* Listed in `requirements.txt (to be made, you should add this once you get the repo running)`


### Install

```sh
pip install -r requirements.txt

```


### Usage

Here's an example. Suppose I filmed a couple of soccer matches. 

```sh
1. In data/raw, make a folder data/raw/soccer, and add those videos to that folder 
2. Find the absolute path of your repository directory. And initialize a shell variable called ROOT_DIR.
   -> ex. ROOT_DIR="/mnt/hbnas/home/fgan/Motion_Generator"
3. run -> python3 src/data/make_dataset.py --base_path $ROOT_DIR --video_directory $ROOT_DIR/data/raw/soccer --extract_directory $ROOT_DIR/data/interim/soccer --feature_directory $ROOT_DIR/data/processed/soccer

```
Under data/processed/soccer, you will find the processed data in two format: "***spatial***" and "***temporal***"

***spatial*** contains motion vectors sequenced spatially, where each row is the flattened sequence of motion vectors for a single frame.

***temporal*** contains motion vectors sequenced temporally, where each row is the sequence of motion vectors for a single 8x8 macroblock. (Yes, 8x8. All are normalized to 8x8 internally). 



## Author

👤 **Felix G**


## 📝 License

This project is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) licensed.

***

+++
title = "Upload a Local Dataset via the CLI"
description = "How to upload images and optionally annotations to Highlighter using the CLI"
date = 2024-03-12T08:00:00+00:00
updated = 2024-03-12T08:00:00+00:00
draft = false
weight = 100
sort_by = "weight"
template = "docs/page.html"

[extra]
lead = "How to upload images and optionally annotations to Highlighter using the CLI"
toc = true
top = false
+++

Sometime you may want to upload images, and other times you may have a labeled
dataset on disk you want to import to Highlighter. This tutorial takes you through
both options.


## Images Only

### Prerequisites
  
This tutorial expects you:

  1. [Highlighter Credentials](docs/how-to-guides/highlighter-credentials.md)
  2. Create a Data Source in the Highlighter Web UI, note the ID from the URL, eg:
  `https://compuglobalhypermeganet.highlighter.ai/data_source/DATASOURCE_ID`


### Upload Images From a Directory

The simplest form is just uploading a directory of files.

The following will upload all files in `--image-dir` to the `--data-source-id`
provided.

Upon completion you will also have a local directory with symlinks mapping the
newly created Highlighter file ids to the original files you uploaded.

```shell
hl image create --data-source-id 123 --image-dir my_images/
```


### Upload Images From a Text File

If you have a text file containing paths to the images you want upload you can
use the `--file` option.

Each path should be on a new line and should be an absolute path or, they can
be relitave paths where `--image-dir` will be prepended to each path in the file.

Upon completion you will also have a local directory with symlinks mapping the
newly created Highlighter file ids to the original files you uploaded.

```
# images.txt
images/00.jpg
images/01.jpg
images/02.jpg
```

```shell

# Upload images with paths in file
hl image create --data-source-id 123 --file images.txt

# Upload images with paths foo/PATH_FROM_TXT_FILE
hl image create --data-source-id 123 --file images.txt --image-dir foo
```

### From a Coco json file

If you have a coco dataset json file you can use the `--file` option.

If needed you can use `--image-dir` to append an directory to the `file_name`s
im the coco image records.

Upon completion you will also have a duplica coco json file with the `.images[].file_
name` values updated to use the newly create Highlighter file ids

```shell
# Upload images with paths image_dir/PATH
hl image create --data-source-id 123 --file coco.json --image-dir foo
```

## Images And Observations

If you have an existing labelled dataset you can upload the images and 
the labels as follows.

**Coco Bounding Box or Polygon segmentaton are the only formats supported from the CLI at the moment**

### Prerequisites
  
This tutorial expects you:

  1. [Highlighter Credentials](./highlighter-credentials.md)
  2. Create a Data Source in the Highlighter Web UI, note the ID from the URL, eg:
  `https://compuglobalhypermeganet.highlighter.ai/data_source/DATASOURCE_ID`
  4. Create the Object Classes on the same name in Highlighter
  3. Create an Assessment Process in Highlighter, note the ID from the URL, eq:
  `https://compuglobalhypermeganet.highlighter.ai/projects/PROCESS_ID`
  5. Add the Object Classes to the Assessment Process
  6. Your Highlighter User Id

### Coco Dataset

Example directory structure

```
annotations/
  train.json
  ...
images/
  ...
```

```shell
# Upload the images, after this you should have a duplicate of train.json
# containing the new Highlighter file ids train_with_hl_ids.json
hl image create --data-source-id 123 \
  --file annotations/train.json \
  --image-dir images

# Upload the labels in the dataset to an Assessment Process
hl submission create-from-dataset \
  --dataset-format coco \
  --data-path annotations/train_with_hl_ids.json \
  --user-id ### \
  --process-id ### \
  --data-source-id ###
```


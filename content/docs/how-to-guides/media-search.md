+++
title = "Media Search"
description = "Using the media search page in Highlighter"
date = 2023-09-26T08:00:00+00:00
updated = 2023-09-26T08:00:00+00:00
draft = false
weight = 10
sort_by = "weight"
template = "docs/page.html"

[extra]
toc = true
top = false
+++

## Navigating to the media search page

Navigate to the media search page by clicking 'Develop' in the top nav then clicking 'Media' => 'Search' in the side nav.

## Anatomy

Firstly you will see a summary of the number of files you are currently seeing. For example if you see '100 of 450 files', that means you currently have 450 results for your current search criteria, but you are only seeing 100 of them because they are paginated. To advance to the next page of results, use the pagination nav in the top right to select a page of results, Next/Prev, or First/Last.

To change the number of results per page, see the section below <a href="#results-per-page">Results Per Page</a>.

## Filters overview

On the left of the page are filters that let you to look at your files in different ways. Set your desired filters then click the 'Search' button at the bottom to see files matching those filters. For example, to see files that match Data Source 'My data source', choose that data source in the Data Sources dropdown then click Search. You can choose multiple filters.

## Actions

Once you have your results, you can take a variety of actions.

### Actions on a single file

1. To view a single file - click the eye icon on the file thumbnail
2. To edit a single file in the annotation tool (only available if an assessment process filter is set) - click the pencil icon on the file thumbnail
3. To download a single file - click the download icon on the file thumbnail

### Actions on all files shown

#### Add to order

To add files to a process order, click the 'Add to Order' button. In the dialog box that appears, select the desired order, then click 'Add Files To Order'. You will see a message confirming the files have been added, or with any errors.

#### Download files

To download files, click the 'Download Files' button. Files will be downloaded one by one. Your browser might prompt you to allow multiple downloads from this site - click 'Allow'. To cancel the download, close the browser window/tab.

## Filters

#### 'Hide/Show Overlays' button

Use this button to hide/show the overlays on individual images that contain annotations/bounding boxes.

#### 'Reset' button

Use this button to reset all filters.

#### 'Only Latest Submissions' tick-box

Tick this box to only show results where the filter criteria only occur in the latest submission on an image.

#### File ID(s)

Use this input for an ID of a file, optionally comma-separated to use multiple IDs. This is the Highlighter database ID of the file.

#### Original Source URL

Use this input for all or part of the original source URL of files. This will match the text in the URL from which the file was original ingested into Highlighter.

#### Content Types

Choose one or more from a list of file content types, for example image, video, audio etc.

#### File Metadata Key

Choose a desired key that exists in the metadata of files. This is used in conjuction with the next filter, File Metadata Value.

#### File Metadata Value

Choose the desired value of the key provided above in File Metadata Key.

#### Data Source

Choose one or more data sources that contain the desired files.

#### Human Assessment Stages

Choose one or more human assessment stages containing the desired files.

#### Checked Out By Users

Choose one or more users who have checked out the desired files in a human assessment stage.

#### Completed in Queue?

Choose whether files have been completed in a human assessment stage or not.

#### Datasets

Choose one or more datasets containing desired files.

#### Assessment Process

Choose one or more assessment processes containing desired files.

#### Assessment Process Order

Choose one of more assessment process orders containing desired files. To use this filter, you need to also set the Assessment Process filter above to the process that contains the selected assessment process order.

#### Capability

Choose one or more capabilities that have made machine assessments on desired files.

#### Training Run

Choose one or more training runs that have made machine assessments on desired files.

#### Machine Assessment Stages

Choose one or more machine assessment stages containing desired files.

#### Object Classes

Choose one or more object classes contained in assessments on desired files.

#### Intersects



#### Without

Choose one or more object classes to return file results with annotations that don't contain them.

#### Submitted by Users

Choose one or more users who made assessments on desired files.

#### Submitted by Roles

Choose one or more roles of users who made assessments on desired files.

#### Annotated by Users

Choose one or more users who made annotations on desired files.

#### Annotation Status

Choose a status of annotations made on desired files.

#### Attributes

Choose one or more attributes present in assessments made on desired files. For each attribute chosen, another input will appear allowing you to select a value for that attribute. The type of the attribute dictates th type of the new input. For example if you choose a string attribute, the new input that appears will be a text box, if you choose an enum attribute, the new input will be a dropdown.

#### Object Status

Choose an object status of assessments made on desired files. For example, if you choose 'Object Identified', files will be returned that have assessments containing annotations.

#### Flagged Assessment

Choose a flagged status on assessments made on desired files. For example, if you choose 'Yes', files will be returned that contained flagged assessments.

#### Files Added

Define a date range within which desired files were added.

#### Assessment Submitted

Define a date range within which assessments were made on desired files.

#### Results per page
To change the number of results per page, scroll down the bottom of the filters section to the Results Per Page dropdown. Choose the desired number of results per page, then click Search. Note - the more results per page, the longer the page will take to load. If the page times out before loading, reduce the number of results per page.

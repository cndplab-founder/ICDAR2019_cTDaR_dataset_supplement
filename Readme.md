# ICDAR2019_cTDaR_dataset_supplement

This repository contains a great supplement to the ICDAR2019 cTDaR dataset in terms of adjacency relations, from <strong>Prof. Cheng-Lin Liu's Group, Institute of Automation, Chinese Academy of Sciences</strong> [1]. 

Thank Cheng-Lin Liu's Group for their helpful contributions!

## Overview

The original ICDAR2019 cTDaR dataset is composed of modern documents and archival documents, and this dataset is extracted and relabeled based on the modern ones.

The following table shows the number of training and test images, which are fully annotated.

|    |  TrainSet | TestSet |
|--- |   :----:  | :----:  | 
|Track A   | 600 | 240 |
|Track B.2  | --  | 100 |


## Annotation Format

```
<?xml version="1.0" encoding="UTF-8"?>
<document filename="cTDaR_t10000.jpg">
    <table>
        <Coords points="113,94 113,449 680,449 680,94"/>
        <cell id="0" neighbors="1:R 4:B 5:L">
            <Coords points="318,94 372,94 372,105 318,105"/>
        </cell>
       ...
        <cell id="12" neighbors="6:T 7:R 11:B">
            <Coords points="112,257 289,257 289,293 112,293"/>
        </cell>
    </table>
</document>
```
For the annotation of dataset, The notation is modified from ICDAR 2019 cTDaR Competition format, appending `<cell/id>` and `<cell/neighbors>` to store the relations between the adjoining cells.

In the XML file, Each `<table>` element corresponds to a table, which contains a single `<Coords>` element with `[points]` attribute to indicates the coordinates of the bounding polygon with 4 vertices. Table contain a list of `<cell>` elements.

Especially in this format, each `<cell>` element has a attribute `[id]` which denotes a unique numerical index for this cell, and a attribute `[neighbors]`, which denotes its left, right, top, bottom adjoining cell id by `[L]`,`[R]`,`[T]`,`[B]` separately.


## Reference
[1] Xiao-Hui Li, Fei Yin, Cheng-Lin Liu. Table Structure Recognition and Form Parsing by End-to-End Object Detection and Relation Parsing. Pattern Recognition.

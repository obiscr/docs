---
title: Getting Started
nav_order: 1
parent: ExcelEditor
---

## Usage

Select excel file, supports multiple opening methods

+ Mouse click to open
+ Shortcut key to open
+ Quick search opens

> `Ctrl Shift D` on **Windows/Linux**, `Command Shift D` on **macOS**

## Home Panel Actions

| Icon        | Description                                   |
|:-------------|:----------------------------------------------|
| ![](https://intellij-icons.jetbrains.design/icons/AllIcons/actions/matchCaseSelected.svg)            | Enable uppercase matching mode                |
| ![](https://intellij-icons.jetbrains.design/icons/AllIcons/actions/wordsSelected.svg) | Enable full character matching mode           |
| ![](https://intellij-icons.jetbrains.design/icons/AllIcons/actions/regexSelected.svg)           | Regular match pattern                         |
| ![](https://intellij-icons.jetbrains.design/icons/AllIcons/actions/previousOccurence.svg)           | Jump to previous search result                |
| ![](https://intellij-icons.jetbrains.design/icons/AllIcons/actions/nextOccurence.svg)           | Jump to next search result                    |
| ![](https://intellij-icons.jetbrains.design/icons/AllIcons/graph/snapToGrid.svg)           | Jump to the specified Cell                    |
| ![](https://intellij-icons.jetbrains.design/icons/AllIcons/general/filter.svg)           | Column filter                                 |
| ![](https://intellij-icons.jetbrains.design/icons/AllIcons/actions/menu-open.svg)           | Show files in Finder/Explorer                 |
| ![](https://user-images.githubusercontent.com/28687074/154850761-db118644-ef2f-4d80-b9b1-f3c95953ee41.svg)           | Call the system's Excel tool to open the file |
| ![](https://intellij-icons.jetbrains.design/icons/DevkitIcons/icons/gutter/diff.svg)           | File Compare                                  |
| ![](https://intellij-icons.jetbrains.design/icons/AllIcons/actions/replace.svg)           | Show Replace Component                        |

### Notice
![](https://intellij-icons.jetbrains.design/icons/AllIcons/actions/wordsSelected.svg) and ![](https://intellij-icons.jetbrains.design/icons/AllIcons/actions/regexSelected.svg) simultaneous opening is not supported

## Compare Panel Actions

| Icon                                                                                      | Description                    |
|:------------------------------------------------------------------------------------------|:-------------------------------|
| ![](https://intellij-icons.jetbrains.design/icons/AllIcons/actions/previousOccurence.svg) | Jump to previous search result |
| ![](https://intellij-icons.jetbrains.design/icons/AllIcons/actions/nextOccurence.svg)     | Jump to next search result     |
| ![](https://intellij-icons.jetbrains.design/icons/AllIcons/actions/refresh.svg)           | Reload files from disk         |
| ![](https://intellij-icons.jetbrains.design/icons/AllIcons/actions/swapPanels.svg)        | Swap the file of to sides      |
| ![](https://intellij-icons.jetbrains.design/icons/AllIcons/vcs/arrow_right.svg)           | Accept the left value          |
| ![](https://intellij-icons.jetbrains.design/icons/AllIcons/vcs/arrow_left.svg)            | Accept the right value         |

## Introduce

### Data modification
There are generally three formats of data: **Date Format**, **Normal Text**, and **Formula**.

#### Date Format
When modifying the date format: the new value written must conform to the standard date format, otherwise the writing will fail and the original value will be restored. That is: the edit was unsuccessful.

![DescEditDate](https://user-images.githubusercontent.com/28687074/154837396-91fe23ab-1e81-41c6-9490-2ab956984784.gif)

#### Normal Text
Normal text data can be written directly.

#### Formula
For formulas, modification will trigger recalculation, and the final value is the value calculated by the tool formula, not the actual written value.

For example:
The value of cell **A1** is: `256`, the value of cell **A2** is `512`, the type of cell **A3** is the formula: `SUM(A1:A2)`. Under normal circumstances, the value of cell **A3** is: 768.
At this point, we modify the value of cell A3 to 1000, which will trigger the formula to recalculate. That is to say, without modifying cell A1 and cell A2, the calculated result of cell A3 is still 768.
**Suppose you modify cell A1 to 1000 before modifying cell A3, then when you modify cell A3, the calculated value should be: 1512, because A3(1512) = A1(1000) + A2(512)**.

![DescEditFormula](https://user-images.githubusercontent.com/28687074/154837384-94199813-e7a9-4819-80fd-6890333b4d19.gif)

### File comparison
The csv files can only be compared with csv files, xls files and xlsx files can be compared with each other arbitrarily

### Excel Merge Function
File Merge supports three modes: **Merge Single Row**, **Merge Multiple Rows**, **Merge All Rows**.
Data writing rules: If you want to write the data on the left to the right, 
click ![](https://intellij-icons.jetbrains.design/icons/AllIcons/vcs/arrow_right.svg). 
In turn, if you want to write the data on the right to the left, 
click ![](https://intellij-icons.jetbrains.design/icons/AllIcons/vcs/arrow_left.svg). 
The direction of the arrow vividly illustrates the direction of the data.

#### Merge Single Row
To merge a single line, you only need to click the ![](https://intellij-icons.jetbrains.design/icons/AllIcons/vcs/arrow_right.svg) 
or ![](https://intellij-icons.jetbrains.design/icons/AllIcons/vcs/arrow_left.svg) 
of the current line.

#### Merge Multiple Rows
To merge the selected rows, just select the data on the left or right and click the merge button on the toolbar.

#### Merge All Rows
To merge all rows, simply click the merge button on the toolbar to merge. 
But you cannot select multiple rows of data before the operation.
That is to say, if you select multiple rows (the number of selected rows is greater than 1 row), 
it will be processed as multi-row merge, and not all rows will be merged.

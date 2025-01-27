# Incorrect Placement of $inc Operator in MongoDB Aggregation Pipeline

This repository demonstrates a common error when using the `$inc` operator within a MongoDB aggregation pipeline. The error occurs when attempting to increment a field *after* a `$limit` stage has already reduced the number of documents.

## Bug

The bug lies in the incorrect placement of the `$inc` operator.  By placing it after `$limit`, the increment only affects those results already returned, not the original dataset before limiting.

## Solution

The correct approach is to perform the increment before the `$limit` stage, ensuring all documents are modified before being limited.
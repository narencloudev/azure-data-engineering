# Databricks Notebook activity

## Purpose
Starts a notebook job in Azure Databricks from an ADF pipeline.

## When to use
Use it when transformations are implemented in Databricks notebooks, often with Spark or Python.

## Example
ADF copies raw files to a lake, then invokes a notebook to transform Bronze data into Silver data.

## Requirements
Configure the Databricks linked service, select the notebook, and pass parameters if required.

## Watch out
Databricks compute may incur charges. Configure job clusters appropriately and terminate compute when no longer needed.

## Exercise
Draw the pipeline handoff from ADF to a notebook and list the parameters the notebook needs.

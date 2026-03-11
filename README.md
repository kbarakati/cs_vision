# YBCO Atom Detection with BlobLoG

This project studies atom detection in **microscopy images** using **Laplacian of Gaussian blob detection (`blob_log`)**.

## Dataset

The YBCO dataset includes different image types, mainly:

- **Bright-field images**
- **Dark-field images**

These images represent the same material under different imaging conditions, so atomic columns can appear very differently in contrast, brightness, noise, and sharpness.

## Problem

The main challenge is using `blob_log` for atom finding across different images.

BlobLoG depends strongly on hyperparameters such as:

- `threshold`
- `max_sigma`
- preprocessing steps like inversion, log scaling, and deconvolution

A parameter setting that works well for one image may fail on another. This is especially true when comparing bright-field and dark-field images, since the atomic features can look very different.

## Why it matters

Real-time hyperparameter tuning is difficult because:

- different images need different settings
- small parameter changes can strongly affect detections
- manual tuning is slow and not robust

## Goal

The goal of this repository is to test BlobLoG-based atom detection on YBCO data and highlight the difficulty of building a single reliable pipeline for all image types.
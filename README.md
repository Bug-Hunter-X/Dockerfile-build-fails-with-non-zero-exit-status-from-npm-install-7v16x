# Dockerfile Build Failure

This repository demonstrates a common error encountered when building Node.js applications with Docker: a non-zero exit status from `npm install`.  The original `Dockerfile` contains the issue, and a corrected version is provided in `Dockerfile-fixed`.

## Problem

The original `Dockerfile` attempts to install dependencies using `npm install`. However, if there are issues with the package.json file or network connectivity during the installation process, this command might fail, resulting in a non-zero exit status and a failed Docker build.

## Solution

The `Dockerfile-fixed` addresses the problem by using a multi-stage build and caching the dependencies. This method enhances build efficiency and resilience to intermittent failures.

## Reproduction Steps

1. Clone the repository.
2. Attempt to build the original `Dockerfile` using `docker build -t my-app .`.
3. Observe the build failure.
4. Build the corrected `Dockerfile-fixed` using `docker build -t my-app-fixed .`.
5. Observe the successful build.

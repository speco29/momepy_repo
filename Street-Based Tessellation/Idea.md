# Enhancing momepy: Adding Support for Street-Based Tessellation (ST)

## Overview

Momepy is a powerful tool for analyzing urban morphology, already supporting Morphological Tessellation (MT) and Enclosed Tessellation (ET). Adding Street-Based Tessellation (ST) will provide a new intuitive tessellation method, enabling the analysis of city blocks defined by natural barriers such as street networks, rivers, and railways.

## Objectives

1. Extend momepy's functionality by implementing Street-Based Tessellation (ST).
2. Create a method that generates city blocks as polygons based on an input street network and other natural barriers.
3. Ensure seamless integration of ST with existing functionalities, maintaining user-friendliness.

## Implementation Steps

### 1. Data Requirements
- **Input**: 
  - Street network geometry (as GeoDataFrame or similar).
  - Optional: Additional natural barriers (e.g., rivers, railways).
- **Output**: 
  - City blocks represented as polygons in a GeoDataFrame.
# TD Copier Tools Package

Two powerful utilities for copying parameters and operators in TouchDesigner.

## Features:

**ParameterCopier:**
- 1:1 accurate parameter copying
- Preserves parameter order
- Copies all parameter types
- Handles expressions and binds
- Replace or skip existing parameters

**OperatorCopier:**
- Batch copy to up to 10 containers
- Optional renaming
- Replace or skip existing operators
- Progress tracking

## Usage:

**ParameterCopier**
1. Set Sourceop (drag & drop)
2. Set Targetop (drag & drop)
3. Toggle Includevalues (on = copy values)
4. Optional: Set Pagefilter (blank = all pages)
5. Click "Copy Parameters" button

**OperatorCopier**
1. Set Sourceop (drag & drop operator to copy)
2. Set Target 1-10 (drag & drop destination containers)
   - Only fill the ones you need, empties are skipped
3. Optional: Set Custom Name (blank = use source name)
4. Toggle Replace (on = replace existing)
5. Click "Copy to Containers" button

The package-level parameters are **bound** to the internal tools, so they stay perfectly in sync!

## Tools Included:

### 1. ParameterCopier
Copies custom parameters between operators with full support for:
- All parameter types (Int, Float, Str, Menu, Pulse, Toggle, etc.)
- Operator references (OP, COMP, TOP, CHOP, SOP, DAT, MAT)
- Headers and separators
- Values, expressions, exports, and binds
- Menu items and parameter properties
- Maintains parameter order in UI

### 2. OperatorCopier
Copies one operator to multiple containers in one click.
- Copies 1 source to up to 10 target locations/containers
- Option to change the operator name on copy
- option to replace existing operator if there is one

## Internal Structure:

Each tool is fully self-contained with its own Python module:

**ParameterCopier**
- copy_logic (textDAT) - Main execution logic
- param_exec (parameterexecuteDAT) - Button handler
- copy_custom_parameters (textDAT) - Embedded Python module
- info (textDAT) - Help text

**OperatorCopier**
- copy_logic (textDAT) - Main execution logic
- param_exec (parameterexecuteDAT) - Button handler
- copy_operator_to_containers (textDAT) - Embedded Python module
- info (textDAT) - Help text

All Python modules are embedded inside their respective tools, making the .tox completely self-contained with no external dependencies.

#### Version: 1.0
#### Author: GRNCH
#### License: None

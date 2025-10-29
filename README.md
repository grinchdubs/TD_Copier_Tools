# TD Copier Tools Package

Two powerful utilities for copying in TouchDesigner.

## Quick Start - Use From Package Level!

You can use both tools directly from the CopierTools component without going inside:


## Features:

**ParameterCopier:**
- 1:1 accurate parameter copying
- Preserves parameter order
- Copies all parameter types
- Handles expressions and binds
- Replace or skip existing parameters

**OperatorCopier:**
- Batch copy to up to 10 containers
- Drag & drop interface
- Optional renaming
- Replace or skip existing operators
- Progress tracking

**Parameter Copier Page:**
1. Set Pcsourceop and Pctargetop
2. Toggle Pcincludevalues
3. Optional: Set Pcpagefilter
4. Click "Copy Parameters" button

**Operator Copier Page:**
1. Set Ocsourceop
2. Set Octarget1-10 (only set the ones you need)
3. Optional: Set Occustomname
4. Toggle Ocreplace
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

**Usage:**
1. Set Sourceop (drag & drop)
2. Set Targetop (drag & drop)
3. Toggle Includevalues (on = copy values)
4. Optional: Set Pagefilter (blank = all pages)
5. Click "Copy Parameters" button

### 2. OperatorCopier
Copies one operator to multiple containers in one click.

**Usage:**
1. Set Sourceop (drag & drop operator to copy)
2. Set Target1-Target10 (drag & drop destination containers)
   - Only fill the ones you need, empties are skipped
3. Optional: Set Customname (blank = use source name)
4. Toggle Replace (on = replace existing)
5. Click "Copy to Containers" button

## Internal Structure:

Each tool is fully self-contained with its own Python module:

**ParameterCopier:**
- copy_logic (textDAT) - Main execution logic
- param_exec (parameterexecuteDAT) - Button handler
- copy_custom_parameters (textDAT) - Embedded Python module
- info (textDAT) - Help text

**OperatorCopier:**
- copy_logic (textDAT) - Main execution logic
- param_exec (parameterexecuteDAT) - Button handler
- copy_operator_to_containers (textDAT) - Embedded Python module
- info (textDAT) - Help text

All Python modules are embedded inside their respective tools, making the .tox completely self-contained with no external dependencies.

## Version: 1.0
## Author: GRNCH
## License: Open Source

---
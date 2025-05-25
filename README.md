# VTR-3D-Architectures

Repsoitory containing VTR architecture XML files for testing VTR 9 against 3D architectures.

## Architecture Types:
1. 3D CB
   - All input and output pins of all grid locations are interlayer
2. 3D CB-O
   - Only output pins of grid locations are interlayer
3. 3D CB-I
   - Only input pins of grid locations are interlayer
4. 3D SB
   - Switch Blocks (SBs) on the grid are 3D.
   - The current configuration being used for 3D SBs are:
     1. All SBs are 3D
     2. The 2D pattern is Wilton and the 3D pattern is subset
     3. All routing channels are connected to the interlayer connections
   - Each 3D SB architecture also comes with it's routing resource graph (rrg)
     - This is done since VTR cannot build these 3D SB architectures (Tested on VTR 8.1.0 not VTR 9.0.0)
     - The RRG is provided as a zip file, make sure to unzip before using by calling `unzip /path/to/3D-SB-RRG.zip`.
     - To use, run VPR using the extra option `--read_rr_graph /path/to/3D-SB-RRG.xml`
   - More 3D SB configurations can be generated and tested using [LaZagna](https://www.arxiv.org/abs/2505.05579)

     - Variations include:
       - Percentage of SBs that are 3D
       - SB vertical and horizontal pattern
       - 3D SB placement in the grid
       - Vertical connectivity percentage of routing channels
      
## Layer Types
Each architecture type comes with 3 different layer configurations:
1. `homo`: 2 layer homogeneous FPGA, where each layer has the same layout
2. `homo_3d`: 3 layer homogeneous FPGA, where each layer has the same layout
3. `hetero`: 2 layer heterogeneous FPGA, where one layer contains CLBs and the other DSPs and BRAMs.

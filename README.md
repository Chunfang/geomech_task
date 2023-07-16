## File list
`geomechanics_assignment.pptx` gives a problem overview.   
`DAS-HF.h5` gives a synthetic data set.  
`ans_sheet.docx` gives a template to write the answers.
## DAS-HF.h5 field explanation
Use HDFWiew `https://www.hdfgroup.org/downloads/hdfview/` to inspect the data field.   
### `dat_well` (nrow by ncol by nframe)
row (400): different coordinates   
column (10): 1:3 three-component displacement [m]; 4 pressure [Pa]; 5:10 six-component stress [Pa]   
frame (61): times of a uniform spacing `dt`.   
**Note**, The time frames include an initial time (t=0) that can be discarded. The stresses are caulicated from solid deformations.  
### `slip_frac` (nrow by ncol by nframe)
row (1370): different fracture pixels   
column (3): three-component fracture slip [m], in strike, dip and normal directions.  
frame (61): time steps.   
### `frac_trac` (nrow by ncol by nframe)
row (1370): fracture pixels   
column (4): 1:3 strike dip and normal traction [Pa], 4 pressure [Pa]   
frame (61): time steps.   
### `xyz_frac` (nrow by ncol)
row (1370): fracture pixels   
column (10): 1:3 x-y-z coordinates [km]; 4:6 strike vectors; 7:9 dip vectors; 10 representative areas [m2] of the fracture pixels. **Note**, these areas are useful for estimating fracture geometry.
### `xyz_well` (nrow by ncol)
row (400): fiber optics (well) measurements   
col (3): x-y-z [km] coordinates.
## Additional model information
### Formation properties:   
Vp = 3000 [m/s]   
Vs = 1723 [m/s]  
Biot's coefficient 1   
matrix permeability 10E-13 [m2]  
fluid viscosity 1E-3 [Pa*s]
### Fracturing injection/flowback sequence:   
Model time 600 [s] with uniform time step of 10 [s].   
First injection cycle starts at 1 [s], at a rate of 0.64 [m3/s] for 100 [s].   
After that, the well is shut-in for 100 [s], zero flow rate.   
The second injection starts after the shut-in, at 0.64 [m3/s] for 100 [s].   
Another shut-in for 100 [s].   
Finally, the flowback starts at 0.256 [m3/s], until the end of the model time. 

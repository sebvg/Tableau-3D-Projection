# Tableau 3D Projection
 An Alteryx macro for projecting and rotating 3D plots in Tableau

tableau_3d_project.yxmc is the Alteryx macro.
It takes X, Y and Z coordinates. It projects along the Z axis, rotating incrementally along X and Y axes.
Increments are calculated so that the macro always performs one full rotation. 
Number of X axis rotations and Number of Y axis rotations start at 0.
The macro will output rows equal to
	n * (Number of X axis rotations + 1)  * (Number of Y axis rotations + 1)
where n is the number of rows in your original data.

Outputs are X_transformed, Y_transformed, X_iteration, Y_iteration, and new_record_id

To construct the plot in tableau, place X_iteration on columns and Y_iteration on rows (both as discrete dimensions).
Place X_transformed and Y_transformed on rows (as discrete dimensions). Change the mark type to circle.
Place colour on color as an attribute. Change the colour to reversed.

The field new_record_id creates a record ID at an equivalent position to using  a record ID before inputting to the macro.
This is for joining reference data before and after using the macro.

This macro only supports visualising at the row level, so you should aggregate to the level of detail you want to visualise
before inputting to the macro.
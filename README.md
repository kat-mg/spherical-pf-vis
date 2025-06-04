# spherical-pf-vis

## MAP GENERATION
- This is used to create the random maps that will be the input for Spherical Anya
- To create a file, run the following command in the terminal:
    "cd map_generation"
    "npm install d3-geo-voronoi"
    "node delauney.js ../sphere_vis/mesh_files/<filename>.sph"
- To adjust the number of points that will be used, at line 133, change the number inside generateRandomPoints(200);
    For example, generateRandomPoints(1000); will use 1000 points
- To adjust the number of obstacles in the map, change the second parameter in the removeTriangles() function in line 135
    For example, removeTriangles(delaunay.triangles.map((x) => x), 0.2); will have 20% obstacles
                 removeTriangles(delaunay.triangles.map((x) => x), 0.x); will have x% obstacles

## SPHERE VISUALIZATION

### GENERAL MESH VISUALIZATION
- Set visRes and visSearchNodes, found in lines 196 and 197, to false if you only wish to visualize the mesh
- To change the color of the obstacles change the hex color code in line 186
- To show where each point in the mesh is, uncomment line 222 (for it to have a label, uncommen line 208)
- To show the outline of each polygon, uncomment line 261 (the color can be altered by changing the hex color code in line 260)

### RESULTS VISUALIZATION
- Set visREs, found in line 196, to true
- In line 293, change "<insert_file_name>" to the appropriate .txt that is to be visualized
- The colors may be changed in line 297 (for the points lines) and line 303 (for the lines)
#### Expected .txt format
- There will be n lines, where n is equal to the number of points traversed there are in the path

### SEARCH NODE VISUALIZATION
- Set visSearchNodes, found in line 197, to true
- In line 267, change "<insert_file_name>" to the appropriate .txt that is to be visualized
- To add a label for each root, uncomment line 277
#### Expected .txt format
- There will be i*3 lines, where i is equal to the number of search nodes there are
- The ith line is the root
- The ith+1 and ith+2 lines are the right and left end point
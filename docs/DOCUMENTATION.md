
### To create your own attackable example 
The `splats` folder contains pre-trained Gaussian Splat scenes.  Using the original project, you need to combine both the input data (before creating splats) and the output data (trained splat scene) into a single folder as follows:
```
<location>
|---distorted
|   |---sparse
|       |---0
|           |---cameras.bin
|           |---images.bin
|           |---points3D.bin
|           |---project.ini
|---images
|   |---<image 0>
|   |---<image 1>
|   |---...
|---input
|   |---<image 0>
|   |---<image 1>
|   |---...
|---point_cloud
|   |---iteration_7000
|   |   |---point_cloud.ply
|   |---iteration_30000
|       |---point_cloud.ply
|---sparse
|   |---0
|       |---cameras.bin
|       |---images.bin
|       |---points3D.bin
|---stereo
|   |---consistency_graphs
|   |---depth_maps
|   |---normal_maps
|   |---fusion.cfg
|   |---patch-match.cfg
|---cameras.json
|---cfg_args
|---input.ply
|---run-colmap-geometric.sh
|---run-colmap-photometric.sh
```

Terminal running command(Inferential video command):
(example)python pipeline.py --config config/infer_cfg_pphuman.yml --video_file=test_video/Python.mp4 --device=gpu --draw_center_traj --do_break_in_counting --region_type=custom --region_polygon 0 884 1681 830 1691 993 0 1032

Meaning of command line parameters:
--video_ File: infers video path

--Device: specifies whether the prediction device is gpu or cpu

--draw_center_Traj: Indicates whether to draw the trace track. If it is not set, it defaults to False.
Note that the test video for drawing the tracking track is best shot by a still camera.

--do_break_in_Counting: Indicates whether to count after area access. If not set, it defaults to False.

--region_Type: Indicates the area of traffic counting, when set --do_break_in_counting, you can only select custom.
The default is custom, which means that the user defined area is used as the entrance and exit.
The coordinates of the midpoint of the lower boundary of the same object frame are from outside the area to inside the area within two adjacent seconds, that is, the count is added by one.

--region_ Polygon: Represents the point coordinate sequence of the polygon in the user-defined area.
Each two is a pair of point coordinates (x, y), which are connected into a closed area in clockwise order.
It requires four pairs of points, that is, eight integers. The default value is [].
You need to set the point coordinates by yourself. If it is a quadrilateral area, the coordinate order is upper left xy, upper right xy, lower right xy, and lower left xy.
The user can run this code to obtain the resolution frame number of the measured video, and can customize and adjust the visualization of the polygon area he wants.

The (Requirement) Environment of this application:
python 3.7
conda 22.9.0
PaddlePaddle >= 2.2.2
PaddleDetection Develop Version
CUDA Version: 11.7
cuDNN Version: 8.4.1 (recommend, if there is no cuDNN, the program may run slowly.)
# actors_sim
It is a seperated package to insert sitting/standing/walking humans inside a simulated environment. This package is Adapted from the [servicesim] package which developed by the OpenSourceRoboticsFoundation OSRF. 
To use this package you need to specify:
- The xy-coordinates for each sitting human and his/her direction (yaw angle). This can be done inside *sitting_human_poses.erb* file
- The xy-coordinates for the standing areas (at which standing human will be inserted), and the number of the standing human per each standing area. This can be done inside the *standing_areas.erb* file.
- The trajectories for walking people in terms of xy-waypoints, the number of human that follow each trajectory, and the velocity of the walking human. This can be done inside the *walking_trajectories.erb* file.

   [servicesim]:<https://bitbucket.org/osrf/servicesim/wiki/Home>

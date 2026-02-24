# perception

A comprehensive ROS 2-based autonomous driving perception stack for Autoware. This repository provides object detection, tracking, segmentation, and multi-sensor fusion capabilities for autonomous vehicle systems.

## Modules

### LiDAR-Based Detection

| Package | Description |
|---------|-------------|
| [autoware_lidar_centerpoint](autoware_lidar_centerpoint/) | 3D object detection using the CenterPoint neural network with TensorRT inference on point clouds |
| [autoware_lidar_transfusion](autoware_lidar_transfusion/) | Multi-modal 3D detection combining LiDAR and camera data using the TransFusion architecture |
| [autoware_lidar_apollo_instance_segmentation](autoware_lidar_apollo_instance_segmentation/) | Point cloud instance segmentation using Apollo's algorithm |
| [autoware_euclidean_cluster](autoware_euclidean_cluster/) | Point cloud segmentation into clusters using Euclidean distance |
| [autoware_ground_segmentation](autoware_ground_segmentation/) | Ground point removal from LiDAR data using ray-based, scan-based, or RANSAC filtering |

### Object Tracking

| Package | Description |
|---------|-------------|
| [autoware_multi_object_tracker](autoware_multi_object_tracker/) | Temporal multi-object tracking using Extended Kalman Filters (EKF) with data association |
| [autoware_radar_object_tracker](autoware_radar_object_tracker/) | Specialized radar-based object tracking with motion models |
| [autoware_bytetrack](autoware_bytetrack/) | Video object tracking using the ByteTrack algorithm |
| [autoware_detection_by_tracker](autoware_detection_by_tracker/) | Creates detections from tracking results |
| [autoware_tracking_object_merger](autoware_tracking_object_merger/) | Merges tracking results from multiple sources |

### Sensor Fusion

| Package | Description |
|---------|-------------|
| [autoware_image_projection_based_fusion](autoware_image_projection_based_fusion/) | Fuses 2D camera detections with 3D LiDAR data via ROI projection and PointPainting |
| [autoware_radar_fusion_to_detected_object](autoware_radar_fusion_to_detected_object/) | Converts radar tracks to detected objects compatible with the fusion pipeline |

### Radar Processing

| Package | Description |
|---------|-------------|
| [autoware_radar_object_clustering](autoware_radar_object_clustering/) | Clusters radar detections |
| [autoware_radar_crossing_objects_noise_filter](autoware_radar_crossing_objects_noise_filter/) | Filters noise from radar detections of crossing objects |
| [autoware_radar_tracks_msgs_converter](autoware_radar_tracks_msgs_converter/) | Converts radar tracking message formats |

### Traffic Light Processing

| Package | Description |
|---------|-------------|
| [autoware_traffic_light_classifier](autoware_traffic_light_classifier/) | Classifies traffic light state (red/yellow/green) using CNN or HSV methods |
| [autoware_traffic_light_fine_detector](autoware_traffic_light_fine_detector/) | Detects traffic lights in images with fine-grain localization |
| [autoware_traffic_light_map_based_detector](autoware_traffic_light_map_based_detector/) | Predicts traffic light locations using map data |
| [autoware_traffic_light_multi_camera_fusion](autoware_traffic_light_multi_camera_fusion/) | Fuses traffic light detections from multiple cameras |
| [autoware_traffic_light_occlusion_predictor](autoware_traffic_light_occlusion_predictor/) | Predicts traffic light occlusion |
| [autoware_traffic_light_arbiter](autoware_traffic_light_arbiter/) | Arbitrates between multiple traffic light detection sources |
| [autoware_traffic_light_visualization](autoware_traffic_light_visualization/) | Visualizes traffic light states |
| [autoware_crosswalk_traffic_light_estimator](autoware_crosswalk_traffic_light_estimator/) | Estimates traffic light state at crosswalks |

### Object Post-Processing & Filtering

| Package | Description |
|---------|-------------|
| [autoware_detected_object_feature_remover](autoware_detected_object_feature_remover/) | Removes unnecessary features from detected objects |
| [autoware_detected_object_validation](autoware_detected_object_validation/) | Validates and filters detected objects |
| [autoware_object_merger](autoware_object_merger/) | Merges detection results from multiple sources |
| [autoware_simple_object_merger](autoware_simple_object_merger/) | Simple merging of object detection results |
| [autoware_cluster_merger](autoware_cluster_merger/) | Merges point cloud clusters from multiple sources |
| [autoware_object_range_splitter](autoware_object_range_splitter/) | Splits objects by detection range for specialized processing |
| [autoware_object_velocity_splitter](autoware_object_velocity_splitter/) | Splits objects by velocity for specialized processing |
| [autoware_shape_estimation](autoware_shape_estimation/) | Estimates bounding box shapes for detected objects |
| [autoware_occupancy_grid_map_outlier_filter](autoware_occupancy_grid_map_outlier_filter/) | Outlier filtering using occupancy grid maps |
| [autoware_raindrop_cluster_filter](autoware_raindrop_cluster_filter/) | Filters rain-related noise from sensor data |

### Map-Based Processing

| Package | Description |
|---------|-------------|
| [autoware_map_based_prediction](autoware_map_based_prediction/) | Predicts object trajectories using map data |
| [autoware_compare_map_segmentation](autoware_compare_map_segmentation/) | Segments objects based on map comparison |
| [autoware_elevation_map_loader](autoware_elevation_map_loader/) | Loads elevation maps for terrain-aware processing |

### Occupancy Grid

| Package | Description |
|---------|-------------|
| [autoware_probabilistic_occupancy_grid_map](autoware_probabilistic_occupancy_grid_map/) | Builds probabilistic occupancy grid maps from sensor data |

### Deep Learning Infrastructure

| Package | Description |
|---------|-------------|
| [autoware_tensorrt_common](autoware_tensorrt_common/) | Common utilities for TensorRT-based inference |
| [autoware_tensorrt_classifier](autoware_tensorrt_classifier/) | Generic classifier wrapper for TensorRT models |
| [autoware_tensorrt_yolox](autoware_tensorrt_yolox/) | YOLOX object detector with TensorRT inference |

### Utilities

| Package | Description |
|---------|-------------|
| [perception_utils](perception_utils/) | Shared utility functions and common libraries for the perception stack |

## Key Dependencies

- **ROS 2** — Middleware framework
- **TensorRT** — GPU-accelerated neural network inference
- **ONNX** — Model exchange format
- **PCL (Point Cloud Library)** — Point cloud processing
- **OpenCV** — Image processing

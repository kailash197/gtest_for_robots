ament_add_test(test_bt_navigator # just a test name
  GENERATE_RESULT_FOR_RETURN_CODE_ZERO
  COMMAND "${CMAKE_CURRENT_SOURCE_DIR}/test_system_launch.py"
  WORKING_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}"
  TIMEOUT 180
  ENV
    TEST_DIR=${CMAKE_CURRENT_SOURCE_DIR}
    TESTER=tester_node.py
    TEST_MAP=${PROJECT_SOURCE_DIR}/maps/map_circular.yaml
    TEST_WORLD=${PROJECT_SOURCE_DIR}/worlds/turtlebot3_ros2_demo.world
    BT_NAVIGATOR_XML=navigate_to_pose_w_replanning_and_recovery.xml
    GAZEBO_MODEL_PATH=${PROJECT_SOURCE_DIR}/models
    ASTAR=True
    CONTROLLER=nav2_regulated_pure_pursuit_controller::RegulatedPurePursuitController
    PLANNER=nav2_navfn_planner/NavfnPlanner
)
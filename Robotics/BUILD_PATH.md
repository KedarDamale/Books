# Build path: a DUM-E-inspired workshop assistant

This path turns the Robotics atlas into an incremental engineering program. The target is a capable, supervised workbench arm and gripper with camera-guided object handling, selected contact skills, diagnosable failures, and optional learned improvements. The fictional robot is an inspiration; each claimed capability must be demonstrated under stated conditions.

The [study map](README.md) provides the full branches, and the [topic index](TOPIC_INDEX.md) provides every reading unit. The selected readings below are prerequisite checkpoints rather than all the study a subsystem could need. Return to their earlier area units and the linked Mathematics/CSE bridges when a concept is missing.

No particular arm size, motor, voltage, payload, camera, budget, or fabrication process has been assumed. Write those requirements first, then use calculations, manufacturer documentation, fabrication constraints, and measurements to choose hardware. A simulation-only deliverable is valid learning evidence, but it must remain labeled as simulation.

## Progression and evidence

| Stage | Capability | Reviewable result |
| --- | --- | --- |
| 00 | [Specify the workshop assistant](#stage-00) | A bounded task specification, workspace drawing, payload and object list, interface map, preliminary hazard analysis, and requirements-to-test matrix. |
| 01 | [Design the load path and joint hardware](#stage-01) | A parametric mechanical concept, motor-and-transmission trade study, load and thermal budgets, and critical-interface drawings. |
| 02 | [Create and validate a virtual arm](#stage-02) | A robot description, simple scene, independent Python kinematics checks, and a documented simulator configuration. |
| 03 | [Instrument and control one joint](#stage-03) | A Rust controller or controller-in-the-loop model with position/current telemetry, homing, fault states, bounded commands, and an independently defined stop path. |
| 04 | [Integrate the arm and calibrate it](#stage-04) | A complete modeled or built arm with calibration records, tool and joint references, tested trajectories, and a measured accuracy budget. |
| 05 | [Build the operator station and robot software boundary](#stage-05) | Python robot coordination, an explicit Rust firmware interface, and a TypeScript operator station using the chosen application stack. |
| 06 | [Complete deterministic grasp and place skills](#stage-06) | A deterministic pick-and-place skill using known object poses, modeled geometry, explicit gripper sensing, and task-state feedback. |
| 07 | [Add calibrated vision and closed-loop object handling](#stage-07) | A camera-to-robot perception pipeline with a geometric baseline, optional YOLO model, pose uncertainty, and vision-guided task execution. |
| 08 | [Add a contact-aware workbench skill](#stage-08) | One bounded pushing, surface-following, insertion, or fixture-based tool-holding skill with a contact model and disengagement behavior. |
| 09 | [Compose a supervised workshop assistant](#stage-09) | An integrated assistant that accepts bounded requests, observes the scene, chooses available skills, reports intent, verifies outcomes, and recovers from known failures. |
| 10 | [Evaluate a learned skill against the classical baseline](#stage-10) | A PyTorch policy or learned residual with reproducible training, simulator contracts, held-out evaluations, and staged transfer evidence. |
| 11 | [Extend the assistant after the stationary tasks work](#stage-11) | An optional mobile manipulation, alternative end-effector, or research extension grounded in the tested stationary system. |

Stages 00–09 establish the main stationary assistant. Stage 10 is a deeper learning branch and can start in simulation alongside the classical work; it is not required to make deterministic pick-and-place work. Stage 11 contains optional extensions. The early projects in domain 30 are usable after their selected prerequisites, without completing every advanced domain first.

<a id="stage-00"></a>

## Stage 00: Specify the workshop assistant

Study first:

- [Workspace payload tasks and success criteria](00_Robot_Goals_and_Engineering_Practice/01_Requirements_and_systems/01_Workspace_payload_tasks_and_success_criteria/book_name.txt).
- [Interfaces architecture and trade studies](00_Robot_Goals_and_Engineering_Practice/01_Requirements_and_systems/02_Interfaces_architecture_and_trade_studies/book_name.txt).
- [Robot energy hazards and stop states](00_Robot_Goals_and_Engineering_Practice/02_Laboratory_foundations/02_Robot_energy_hazards_and_stop_states/book_name.txt).
- [Verification validation and engineering notebooks](00_Robot_Goals_and_Engineering_Practice/01_Requirements_and_systems/03_Verification_validation_and_engineering_notebooks/book_name.txt).

Deliverable: A bounded task specification, workspace drawing, payload and object list, interface map, preliminary hazard analysis, and requirements-to-test matrix.

Completion evidence: Every intended capability has an observable success criterion. Reach, payload, precision, timing, energy, stop, and restart requirements are explicit or marked as measurements to establish. Fictional behavior has been translated into testable physical tasks.

<a id="stage-01"></a>

## Stage 01: Design the load path and joint hardware

Study first:

- [Static equilibrium and joint reactions](02_Structures_and_Materials/01_Loads_stress_and_deflection/01_Static_equilibrium_and_joint_reactions/book_name.txt).
- [Beam bending deflection and stiffness](02_Structures_and_Materials/01_Loads_stress_and_deflection/03_Beam_bending_deflection_and_stiffness/book_name.txt).
- [Bearings shafts and alignment](03_Mechanisms_and_Machine_Elements/01_Joints_and_constraint_design/02_Bearings_shafts_and_alignment/book_name.txt).
- [Gears ratios backlash and reflected inertia](03_Mechanisms_and_Machine_Elements/02_Transmission_design/01_Gears_ratios_backlash_and_reflected_inertia/book_name.txt).
- [Joint actuator and gearbox sizing](06_Actuators_Motors_and_Drives/01_Motor_models_and_selection/03_Joint_actuator_and_gearbox_sizing/book_name.txt).
- [Drawings datums fits and tolerance stacks](04_CAD_Fabrication_and_Metrology/01_Parametric_design_and_drawings/03_Drawings_datums_fits_and_tolerance_stacks/book_name.txt).

Deliverable: A parametric mechanical concept, motor-and-transmission trade study, load and thermal budgets, and critical-interface drawings.

Completion evidence: The design accounts for link mass, payload, gravity, acceleration, friction, duty cycle, bearing reactions, deflection, backlash, and assembly tolerance. A limiting case can be checked by hand. Selected component ratings come from their actual documentation.

<a id="stage-02"></a>

## Stage 02: Create and validate a virtual arm

Study first:

- [Homogeneous transforms and frame trees](10_Rigid_Geometry_and_Coordinate_Frames/01_Rotations_and_transforms/03_Homogeneous_transforms_and_frame_trees/book_name.txt).
- [Kinematic chains and forward kinematics](11_Arm_Kinematics_and_Workspaces/01_Forward_and_inverse_kinematics/01_Kinematic_chains_and_forward_kinematics/book_name.txt).
- [Mass inertia and energy models](12_Robot_Dynamics_and_Contact_Models/01_Rigid_body_dynamics/01_Mass_inertia_and_energy_models/book_name.txt).
- [URDF SDF MJCF and consistent robot assets](17_Simulation_and_Digital_Twins/01_Robot_models_and_simulators/01_URDF_SDF_MJCF_and_consistent_robot_assets/book_name.txt).
- [MuJoCo actuators contacts and Python loops](17_Simulation_and_Digital_Twins/01_Robot_models_and_simulators/02_MuJoCo_actuators_contacts_and_Python_loops/book_name.txt).
- [Simulator validation and reality gap budgets](17_Simulation_and_Digital_Twins/02_Model_based_experiments_and_validation/02_Simulator_validation_and_reality_gap_budgets/book_name.txt).

Deliverable: A robot description, simple scene, independent Python kinematics checks, and a documented simulator configuration.

Completion evidence: Known poses agree across the CAD, robot description, and simulator. Mass, center of mass, joint axes, limits, tool frames, and collision geometry are consistent. The report identifies which physical behavior remains unvalidated.

<a id="stage-03"></a>

## Stage 03: Instrument and control one joint

Study first:

- [Encoders homing and position references](08_Sensors_and_Instrumentation/01_Internal_robot_sensing/01_Encoders_homing_and_position_references/book_name.txt).
- [Bare metal startup memory and peripherals](09_Embedded_Rust_and_Real_Time_Control/01_Firmware_and_peripheral_interfaces/01_Bare_metal_startup_memory_and_peripherals/book_name.txt).
- [Control state machines watchdogs and fault latches](09_Embedded_Rust_and_Real_Time_Control/02_Deterministic_loops_and_communication/02_Control_state_machines_watchdogs_and_fault_latches/book_name.txt).
- [Task priorities jitter and deadline budgets](09_Embedded_Rust_and_Real_Time_Control/02_Deterministic_loops_and_communication/01_Task_priorities_jitter_and_deadline_budgets/book_name.txt).
- [PID feedforward and anti windup](13_Feedback_and_Motion_Control/01_Feedback_and_linear_control/02_PID_feedforward_and_anti_windup/book_name.txt).
- [Instrumented single joint project](30_Workshop_Assistant_Integration_Projects/01_Component_and_arm_integration/01_Instrumented_single_joint_project/book_name.txt).

Deliverable: A Rust controller or controller-in-the-loop model with position/current telemetry, homing, fault states, bounded commands, and an independently defined stop path.

Completion evidence: Measured or simulated motion, command age, timing jitter, saturation, current, and temperature are compared with the joint specification. Reset, sensor loss, stale commands, jam, and power-loss behavior are exercised. Physical motion tests begin only after the relevant power, stop, and mechanical test conditions have been verified.

<a id="stage-04"></a>

## Stage 04: Integrate the arm and calibrate it

Study first:

- [Joint offsets scales and repeatability](15_Calibration_and_System_Identification/01_Geometric_and_sensor_calibration/01_Joint_offsets_scales_and_repeatability/book_name.txt).
- [Compliance backlash and task accuracy budgets](15_Calibration_and_System_Identification/02_Dynamic_identification_and_error_budgets/02_Compliance_backlash_and_task_accuracy_budgets/book_name.txt).
- [Trajectory profiles and jerk limits](13_Feedback_and_Motion_Control/02_Robot_servo_architectures/02_Trajectory_profiles_and_jerk_limits/book_name.txt).
- [Computed torque and gravity compensation](13_Feedback_and_Motion_Control/02_Robot_servo_architectures/03_Computed_torque_and_gravity_compensation/book_name.txt).
- [Arm mechanics firmware and calibration project](30_Workshop_Assistant_Integration_Projects/01_Component_and_arm_integration/02_Arm_mechanics_firmware_and_calibration_project/book_name.txt).

Deliverable: A complete modeled or built arm with calibration records, tool and joint references, tested trajectories, and a measured accuracy budget.

Completion evidence: Repeatability and absolute accuracy are reported separately across workspace, payload, and motion direction. Tracking and holding behavior stay within the defined test envelope. Changes to geometry, firmware, tool, or calibration are versioned together.

<a id="stage-05"></a>

## Stage 05: Build the operator station and robot software boundary

Study first:

- [Python nodes topics services and actions](16_Robot_Software_and_ROS2/01_ROS_communication_and_robot_models/01_Python_nodes_topics_services_and_actions/book_name.txt).
- [QoS executors callbacks and freshness](16_Robot_Software_and_ROS2/01_ROS_communication_and_robot_models/02_QoS_executors_callbacks_and_freshness/book_name.txt).
- [ros2 control hardware interfaces and update loops](16_Robot_Software_and_ROS2/02_Hardware_control_and_lifecycle/01_ros2_control_hardware_interfaces_and_update_loops/book_name.txt).
- [TypeScript operator UI and command authority](16_Robot_Software_and_ROS2/02_Hardware_control_and_lifecycle/04_TypeScript_operator_UI_and_command_authority/book_name.txt).
- [Operator station and deterministic motion project](30_Workshop_Assistant_Integration_Projects/01_Component_and_arm_integration/03_Operator_station_and_deterministic_motion_project/book_name.txt).

Deliverable: Python robot coordination, an explicit Rust firmware interface, and a TypeScript operator station using the chosen application stack.

Completion evidence: The UI distinguishes measured state, desired state, task progress, stale data, and faults. Invalid goals, reconnects, cancellation, mode transitions, and remote command authority are tested. Browser responsiveness is not used as evidence for servo timing.

<a id="stage-06"></a>

## Stage 06: Complete deterministic grasp and place skills

Study first:

- [Gripper geometry aperture and object constraints](19_Grasping_and_Contact_Manipulation/01_Grippers_and_grasp_mechanics/01_Gripper_geometry_aperture_and_object_constraints/book_name.txt).
- [Grip force slip and object damage limits](19_Grasping_and_Contact_Manipulation/01_Grippers_and_grasp_mechanics/03_Grip_force_slip_and_object_damage_limits/book_name.txt).
- [Configuration spaces and collision distances](18_Motion_Planning_and_Trajectory_Optimization/01_Geometric_motion_planning/01_Configuration_spaces_and_collision_distances/book_name.txt).
- [MoveIt planning scenes pipelines and execution](18_Motion_Planning_and_Trajectory_Optimization/02_Optimization_and_execution/02_MoveIt_planning_scenes_pipelines_and_execution/book_name.txt).
- [Pregrasp approach lift and place sequences](19_Grasping_and_Contact_Manipulation/02_Pick_place_and_contact_skills/01_Pregrasp_approach_lift_and_place_sequences/book_name.txt).

Deliverable: A deterministic pick-and-place skill using known object poses, modeled geometry, explicit gripper sensing, and task-state feedback.

Completion evidence: Acquisition, lifting, carrying, placement, and release are confirmed from observations. The held object updates collision geometry. Failed grasp, obstruction, dropped object, and failed release lead to defined outcomes and recovery.

<a id="stage-07"></a>

## Stage 07: Add calibrated vision and closed-loop object handling

Study first:

- [Camera intrinsics distortion and reprojection](15_Calibration_and_System_Identification/01_Geometric_and_sensor_calibration/02_Camera_intrinsics_distortion_and_reprojection/book_name.txt).
- [Hand eye base camera and tool transforms](15_Calibration_and_System_Identification/01_Geometric_and_sensor_calibration/03_Hand_eye_base_camera_and_tool_transforms/book_name.txt).
- [Homographies fiducials and PnP pose](20_Computer_Vision_and_3D_Perception/01_Images_features_and_pose/03_Homographies_fiducials_and_PnP_pose/book_name.txt).
- [YOLO training validation and tracking](21_Learned_Perception_and_Visuomotor_Representations/01_Data_and_visual_models/02_YOLO_training_validation_and_tracking/book_name.txt).
- [Detection to 3D pose and grasp candidates](21_Learned_Perception_and_Visuomotor_Representations/02_Perception_for_action/01_Detection_to_3D_pose_and_grasp_candidates/book_name.txt).
- [Calibrated camera pick and place project](30_Workshop_Assistant_Integration_Projects/02_Perception_contact_and_task_integration/01_Calibrated_camera_pick_and_place_project/book_name.txt).

Deliverable: A camera-to-robot perception pipeline with a geometric baseline, optional YOLO model, pose uncertainty, and vision-guided task execution.

Completion evidence: Evaluate objects and conditions excluded from fitting and training. Report pose error, detection errors, latency, end-to-end success, failed grasps, abstentions, and recovery. A high class-confidence score cannot substitute for metric pose or collision checks.

<a id="stage-08"></a>

## Stage 08: Add a contact-aware workbench skill

Study first:

- [Cartesian impedance and admittance](13_Feedback_and_Motion_Control/03_Contact_aware_control/01_Cartesian_impedance_and_admittance/book_name.txt).
- [Force motion selection and hybrid control](13_Feedback_and_Motion_Control/03_Contact_aware_control/02_Force_motion_selection_and_hybrid_control/book_name.txt).
- [Pushing insertion and contact modes](19_Grasping_and_Contact_Manipulation/02_Pick_place_and_contact_skills/02_Pushing_insertion_and_contact_modes/book_name.txt).
- [Tool use payload changes and fixture design](19_Grasping_and_Contact_Manipulation/02_Pick_place_and_contact_skills/03_Tool_use_payload_changes_and_fixture_design/book_name.txt).
- [Contact aware fixture or tool task project](30_Workshop_Assistant_Integration_Projects/02_Perception_contact_and_task_integration/02_Contact_aware_fixture_or_tool_task_project/book_name.txt).

Deliverable: One bounded pushing, surface-following, insertion, or fixture-based tool-holding skill with a contact model and disengagement behavior.

Completion evidence: Compare forces, tracking, saturation, and recovery with a position-only baseline. Vary stiffness, friction, alignment, and payload within the stated test envelope. Tool changes update geometry, mass, frames, and limits.

<a id="stage-09"></a>

## Stage 09: Compose a supervised workshop assistant

Study first:

- [Skills preconditions postconditions and state machines](23_Task_Autonomy_and_Human_Robot_Interaction/01_Task_logic_and_world_state/01_Skills_preconditions_postconditions_and_state_machines/book_name.txt).
- [Task and motion planning with uncertain objects](23_Task_Autonomy_and_Human_Robot_Interaction/01_Task_logic_and_world_state/02_Task_and_motion_planning_with_uncertain_objects/book_name.txt).
- [Language requests typed goals and bounded execution](23_Task_Autonomy_and_Human_Robot_Interaction/01_Task_logic_and_world_state/03_Language_requests_typed_goals_and_bounded_execution/book_name.txt).
- [Intent feedback mental models and trust](23_Task_Autonomy_and_Human_Robot_Interaction/02_Human_factors_and_collaboration/01_Intent_feedback_mental_models_and_trust/book_name.txt).
- [Fault injection HIL and regression scenarios](29_Robustness_Safety_and_System_Validation/02_Fault_injection_monitoring_and_maintenance/01_Fault_injection_HIL_and_regression_scenarios/book_name.txt).
- [Bounded workshop assistant project](30_Workshop_Assistant_Integration_Projects/02_Perception_contact_and_task_integration/03_Bounded_workshop_assistant_project/book_name.txt).

Deliverable: An integrated assistant that accepts bounded requests, observes the scene, chooses available skills, reports intent, verifies outcomes, and recovers from known failures.

Completion evidence: Ambiguous references and unsupported tasks are rejected or clarified. Interruptions and failed postconditions preserve coherent state. Success is measured over complete episodes, including recovery and operator intervention, rather than selected video clips.

<a id="stage-10"></a>

## Stage 10: Evaluate a learned skill against the classical baseline

Study first:

- [Gymnasium environment contracts and resets](24_Reinforcement_Learning_Foundations/02_Learning_from_experience/03_Gymnasium_environment_contracts_and_resets/book_name.txt).
- [Reward design shaping and evaluation protocols](24_Reinforcement_Learning_Foundations/02_Learning_from_experience/04_Reward_design_shaping_and_evaluation_protocols/book_name.txt).
- [PPO clipping on policy data and diagnostics](25_Deep_Reinforcement_Learning_with_PyTorch/02_Continuous_control_algorithms/01_PPO_clipping_on_policy_data_and_diagnostics/book_name.txt).
- [SAC entropy temperature and stochastic actors](25_Deep_Reinforcement_Learning_with_PyTorch/02_Continuous_control_algorithms/03_SAC_entropy_temperature_and_stochastic_actors/book_name.txt).
- [Behavior cloning demonstrations and covariate shift](26_Imitation_Learning_and_Sim_to_Real/01_Demonstrations_and_offline_learning/01_Behavior_cloning_demonstrations_and_covariate_shift/book_name.txt).
- [Dynamics randomization latency and system ID](26_Imitation_Learning_and_Sim_to_Real/02_Transfer_and_deployment_evidence/02_Dynamics_randomization_latency_and_system_ID/book_name.txt).
- [Learned skill with classical baseline project](30_Workshop_Assistant_Integration_Projects/03_Learning_and_optional_mobility/01_Learned_skill_with_classical_baseline_project/book_name.txt).

Deliverable: A PyTorch policy or learned residual with reproducible training, simulator contracts, held-out evaluations, and staged transfer evidence.

Completion evidence: Compare interaction budget, compute, successful tasks, constraint violations, failures, recovery, and multiple seeds. Test unseen initial states and parameter changes. Transfer proceeds through replay and bounded execution with versioned artifacts and independent runtime limits. A result that fails to beat the baseline is retained as useful evidence.

<a id="stage-11"></a>

## Stage 11: Extend the assistant after the stationary tasks work

Study first:

- [Base placement and mobile manipulation](22_Localization_Mapping_and_Navigation/02_Navigation_and_mobile_manipulation/03_Base_placement_and_mobile_manipulation/book_name.txt).
- [Mobile platform stability traction and payloads](28_Mobile_Legged_Aerial_and_Soft_Robotics/01_Locomotion_and_dynamic_balance/01_Mobile_platform_stability_traction_and_payloads/book_name.txt).
- [Mobile manipulator extension project](30_Workshop_Assistant_Integration_Projects/03_Learning_and_optional_mobility/02_Mobile_manipulator_extension_project/book_name.txt).
- [Cross embodiment datasets and transfer](31_Research_and_Advanced_Frontiers/01_Research_evidence_and_generalization/02_Cross_embodiment_datasets_and_transfer/book_name.txt).
- [Vision language action models and limits](31_Research_and_Advanced_Frontiers/01_Research_evidence_and_generalization/03_Vision_language_action_models_and_limits/book_name.txt).

Deliverable: An optional mobile manipulation, alternative end-effector, or research extension grounded in the tested stationary system.

Completion evidence: Reevaluate stability, reachability, localization uncertainty, collision geometry, sensing, and task success for the new embodiment. A transfer or generalist-model claim is tied to the actual tested objects, tasks, and robot configuration.

## Reusable experiment record

For each milestone, preserve:

- Requirement, question, and predicted outcome, with units and reference frames.
- Mechanical, electrical, firmware, model, calibration, dataset, and software versions.
- Inputs, initial conditions, load, environment, timestamps, and operating mode.
- Baseline, method, measurement process, and uncertainty assumptions.
- Results across repeated trials and held-out conditions, including unsuccessful trials.
- Fault and recovery behavior, observed limits, and reasons to revise the design.
- A concrete decision: advance, repeat a measurement, correct a model, or redesign a subsystem.

A useful assistant is an integrated result: the load path, power system, sensing, firmware, calibration, controllers, planner, perception, task logic, and operator interaction must agree about the same physical system. Demonstrating one component does not establish the complete task behavior.

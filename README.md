# characterization-notes (07/04/2021)

The notes below are lessons learned and hints from characterizing a robot drivetrain.

The notes below follow the instructions at: https://docs.wpilib.org/en/latest/docs/software/pathplanning/robot-characterization/index.html

## [Generating a Project](https://docs.wpilib.org/en/latest/docs/software/pathplanning/robot-characterization/generating-project.html)
1. [Project Location](https://docs.wpilib.org/en/latest/docs/software/pathplanning/robot-characterization/generating-project.html#select-project-location)
   - Create a folder within the current java project and save all the config files, data files and screen captures within this folder for easy reference at a later date.
   - Name the folder “Characterization”   
2. [Configure Project Parameters](https://docs.wpilib.org/en/latest/docs/software/pathplanning/robot-characterization/generating-project.html#configure-project-parameters)
   - As of 2021 we are standardizing our drivetrain using Falcon 500 and the integrated TalonFX motor controllers.  
   - The CAN IDs are 12, 13 for the left side and 10, 11 for the right side.
   - Set all “motorsInverted” settings to ‘False’ since the TalonFX motor controller handles the inversion.  The only affect of this is that the distance travelled will have one side positive and the other negative.  This does not appear to effect the data analysis.  
   - If the robot spins in place when doing the first test this means the inverts are not correct.
   - Use 8192 (2048 *4) for the edges per revolution.
   - The units should be meters as WPILIB Trajectory Following uses meters.

There is an example config [.txt](/Drivetrain_example.txt) file in the repository.
## [Deploying a Project](https://docs.wpilib.org/en/latest/docs/software/pathplanning/robot-characterization/deploying-project.html)
The characterization documentation doesn’t do a good job at explaining the notes below.  We have found that there are dependencies that need to be downloaded from the web while deploying a project.  Not following those notes will most likely cause deploying the project to fail. 
  1.	Connect your computer directly to the RoboRIO using a USB cable.
  2.	Connect your computer to a Hot Spot that is not connected to the school Wi-Fi.  The school Wi-Fi will block the needed connection.
  3.	After a successful deploy you do not need to follow the two above notes as long as another program has not been deployed.

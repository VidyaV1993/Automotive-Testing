# CAPL for CAN
 * This repo represents the basic functionalities of Vector CANoe and CAPL used for testing ECUs in automoitive domain. 
 * There are two configuration files in this repo created using Vector CANoe in which the ECUs are programmed using CAPL.
### Raw_cfg ###
  * This configuration consists of two ECUs in which one sends a raw cyclic message 11 56 with ID 300 every 100 ms. 
  * The other ECU is programmed to give a response back ona key event 'k'. 
  * On pressing 'k', a message AB 12 0C with ID 467 appears and in repsponse to this, another message AA with ID 130 appears.
### ECU_cfg ###  
#### This configuration consists of two ECUs a VehicleMotion ECU and a Test ECU.   
#### The other elements of this simulation are CAN Network and an Interactive Generator (IG) block. 
#### A database Transmission DBC file is added to the IG block which consists of three messages with their corresponding data, ID etc.
  * AccelerationMsg - Gives the Acceleration
  * BreakMsg - Gives the BreakStatus
  * VehicleMotion - Gives the Velocity and EngineRunning	
#### This VehicleMotion ECU does the following:
  * On configuration start, EngineRunning is set to 1. This output is displayed every 100 ms.
  * On Acceleration message receival, engine should update the velocity.
  * On break, velocity should be set to 0.
#### The above requirements can be tested using the IG block to send acceleration and break messages or using the Test ECU.
#### The Test ECU does the following: 
  * On key event 'a', acceleration is incremented by 1 and the hence the velocity is incremented as well.
  * On key event 'd', acceleration is decremented by 1 and the hence the velocity is decremented as well.
  * On key event 'b', break is applied by setting break status to 1 and the hence the velocity is set to 0.
#### The log files for the simulation are present in the folder logs_canoe.
		
				
				
           

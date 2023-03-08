#include "vex.h"


using namespace vex;


int displayPositionLoop() {


 Brain.Screen.setFont(mono60);
  while (true) {
   Brain.Screen.clearScreen();


   // Display the X position on row 1
   Brain.Screen.setCursor(1, 1);
   Brain.Screen.print("X: %.3f", RoboticArm1.getAxisPosition(xaxis));


   // Display the Y position on row 2
   Brain.Screen.newLine();
   Brain.Screen.print("Y: %.3f", RoboticArm1.getAxisPosition(yaxis));


   // Display the Z position on row 3
   Brain.Screen.newLine();
   Brain.Screen.print("Z: %.3f", RoboticArm1.getAxisPosition(zaxis));


   wait(0.2, seconds);
 }
 return 0;
}


// This is the function we want to run when the emergency stop button
// is pressed. It will tell the arm to stop moving.
void onEStopPressed() {
 RoboticArm1.emergencyStop();
}


int main() {
 // Initializing Robot Configuration. DO NOT REMOVE!
 vexcodeInit();
  // Link the emergency stop button pressed event with the onEStopPressed function
 EStop.pressed(onEStopPressed);


 // Start task to continuously display the current arm position
 vex::task displayPositionTask(displayPositionLoop);


 // Set up the arm with the initial configuration values
 RoboticArm1.setMasteringValues(1843,2171,1966,369);
 RoboticArm1.setToolTipOffset(0.0, 0.0, 0.0);


 int startX = 5;
 int startY = -4;
 double startZ = 1.75;
 //V
 RoboticArm1.moveToPositionLinear(startX, startY, 4);
 wait(1,sec);
 RoboticArm1.moveToPositionLinear(startX, startY, startZ);
 RoboticArm1.moveToPositionLinear(startX+2, startY+1, startZ);
 wait(1,sec);
 RoboticArm1.moveToPositionLinear(startX, startY+2, startZ);
 wait(1,sec);
 RoboticArm1.moveToPositionLinear(startX, startY+2, 4);
 wait(1,sec);
   //E
 int eX = 5;
 int eY = -1;


  RoboticArm1.moveToPositionLinear(eX-2, eY+1.5, 4);
 wait(1,sec);
 RoboticArm1.moveToPositionLinear(eX, eY+1.5, startZ);
 RoboticArm1.moveToPositionLinear(eX, eY, startZ);


 wait(1,sec);
 RoboticArm1.moveToPositionLinear(eX+2, eY, startZ);
 wait(1,sec);
 RoboticArm1.moveToPositionLinear(eX+2, eY+1.5, startZ);
 RoboticArm1.moveToPositionLinear(eX+2, eY+1.5, 4);
 wait(1,sec);
 RoboticArm1.moveToPositionLinear(eX+1, eY, 4);
 RoboticArm1.moveToPositionLinear(eX+1, eY-0.25, startZ);
 RoboticArm1.moveToPositionLinear(eX+1, eY+1.5, startZ);
 RoboticArm1.moveToPositionLinear(eX+1, eY+1.5, 4);


//X
 int xX = 5;
 int xY = 2;


 RoboticArm1.moveToPositionLinear(xX+1, xY+1.5, 4);
 RoboticArm1.moveToPositionLinear(xX, xY, startZ);
 RoboticArm1.moveToPositionLinear(xX+2, xY+2.5, startZ);
 RoboticArm1.moveToPositionLinear(xX+2, xY+2.5, 4);
 RoboticArm1.moveToPositionLinear(xX, xY+2.5, 4);
 RoboticArm1.moveToPositionLinear(xX, xY+2.5, startZ);
 RoboticArm1.moveToPositionLinear(xX+2, xY, startZ);
}

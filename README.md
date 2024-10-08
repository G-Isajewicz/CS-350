# CS-350
Embedded Systems and Architecture

  This is the final project for the CS-350 course. The project required the creation of embedded software to work with the TI CC3220x LauchXL board to serve as a thermostat device. 
Accomplishing this requried the use of I2C, GPIO, and UART peripherals, as well as the implementation of a task scheduler in order to read input from a temperature sensor, send that data to a server via Wi-Fi (simulated), and handle both the activation of a heater element (simulated) as well as illuminate an LED light as an indicator that the element has been turned on. In order to function as a thermostat the program needed to maintain a set point - the desired temperature - and a method of adjusting the set point according to the input of two buttons - one to increase, one to decrease. The software also required that a message be displayed containing the room temperature taken from a reading of the temperature sensor, the current set point, the 1/0 state of the (hypothetical) heating element, and the runtime in seconds. 

  I believe that I did particularly well in identifying the logical flow of this program prior to coding it. I was able to understand the function of each different componant and peripheral, and develop a flowchart to illustarte the logic. From that point, the application of that logic was fairly attainable. Understanding the exact flow and logic of the program also assisted in the debug process. While debugging, I was able to see where a bug or flaw arose, and deduced where in the code it is likely to be stemming from. Another aspect that I am proud of in this project, although less indentifiable in the finished product, is the work I did translating the previous UART version of the provided code into the updated UART2 version. This involved quite a bit of examining, searching, and reading through documentation for the peripherals, however I was successful and also gained valuable experience reading and understanding code documentation and implementation. That is a skill that I believe will be particularly transferrable to other projects and coursework moving forward. 

  One aspect that I believe I could improve upon is the implementation of the task scheduler. While my finished product is functional, I have a suspicion that there may be a more efficient method of implementation than the one I used. Of course, if I knew exactly what that better method was I would have used it. If I had additional time to fine tune this program, that would be one area I would explore further. 

  In order to ensure that the project is maintainable, readable, and adaptable, I made a deliberate effort to follow best practices in the structure and naming conventions of my code, as well as the inclusion
of comments where necessary. With these standards upheld, and thorough commenting of the functionality of each section, the code should be easily understood by anyone who would be tasked with maintaining or 
modifying it in the future. A level of adaptability is inherent in this code by the nature of its structure. The program uses peripherals to engage with a board, and their implementation is well-commented in 
the code itself. Adding additional functionality, or adapting the code to provide additional functionality should be as simple as identifying that area of the code either from the code itself, or from the
comments, and modifying appropriately. For example, if a temperature range limit is desired for the set point, a simple solution could be found by locating the method of handling the button input that adjusts
the set point and adapting it to include an IF statement check such that if the user pressed the button to increase the temperature:

    
    if(setPoint >= maxSetPoint) {
      setPoint == minSetPoint;
    }
      

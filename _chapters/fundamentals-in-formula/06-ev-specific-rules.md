---
title: EV-Specific Rules
chapter: 5
part: 1
---

*This part covers Section EV in the rulebook.*

Just like the Chassis and Structural section, there are a LOT of rules here. The electrical system is a huge energy storage device due to the vehicle battery, and therefore there are many regulations that need to be followed in order to make sure that everyone’s custom-made battery can be operated and worked on safely. It is impossible to overstate the importance of safety in regards to the battery and the work performed on it; these are high voltage systems, and high voltage carries with it some inherent safety hazards/risks. High voltage is not impossible to work with, and there are procedures that make things perfectly safe, but you *must* abide by them. When treated carelessly, high voltage exposure has very permanent consequences on those that it comes in contact with. Think of it like woodworking tools like drills and saws - immensely useful when operated safely, and immensely dangerous when not respected. 

### Definitions

This is the first part of the EV section, and for good reason. The rules lay out a lot of useful definitions and terms that the other locations in the book refer to. I’ll copy the most helpful ones here:

- Cell
    - This is the basic unit of a vehicle battery. There are many different forms of them, but you can think of them as bigger versions of common consumer AA batteries. Here’s a picture of a commonly used 2170 cell:

    ![2170 battery cell]({{ "/assets/images/fundamentals-in-formula/2170-cell.png" | relative_url }})
    
- Module
    - This is a group of cells. When designing batteries for EVs, it is common to link your cells in a certain “configuration”, which describes how many cells you have linked in series and how many in parallel. At a simple level, this changes how powerful your battery can be (series) vs. how long it can last (parallel). We’ll get into more details in the specific mini-book.
- Tractive Battery
    - This is a group of modules. Usually, you link 6-8 modules together in series to form your overall vehicle battery. The organizers use the term “Tractive” to indicate that this battery is intended to store and supply energy to your “tractive system”, or drive motor. In years past, this has been called the “accumulator”. All of the terminology means the same thing: its the main vehicle battery powering your motor.
- Tractive System
    - This term is meant to describe all of the electrical components that are part of your high-voltage path. Everything that is directly related to making the motor spin.
- Grounded Low Voltage
    - This term means all of the electrical system that is not a part of the Tractive System. The operating voltages of the non-Tractive Systems will typically be around 12 volts, which is “Low Voltage” in relation to your Tractive System, which might be up at 450 volts. The tractive system is also a “floating” system, because it uses its own positive and negative conduction paths to connect to it’s devices, as opposed to a “grounded” system, which just uses the car’s big metal frame as the ground reference point for all of the low voltage devices. This is why you always see the bright orange high voltage wires in pairs - a positive and a negative.

*Rule EV.1*

### Energy Meter

In order to monitor your energy usage during the competition, the organizers mandate the use of an energy meter. It is a small device that needs to fit in your tractive system. They use it to measure the power output of the vehicle at any time and to measure how much energy you are using, which is how they score the Efficiency event. 

*Rule EV.3.2*

### Power & Energy Limits

The maximum power output of the car is limited in the rules to 80 kW. This means that if your car had a really really long straight to just go full power, it would need to limit it’s power to 80 kW. This limit is imposed for safety reasons. You shouldn’t feel disappointed - this is still very, *very* powerful for such light vehicles. You’ll also see that it is difficult to consistently get your car up to 80 kW output. If you tried to transmit max power from a dead stop, your wheels would spin, which would get you nowhere. We’ll explore this limit more in [*Simulate in Formula*]({{ "/books/simulate-in-formula/" | relative_url }}), as we explore the specifics about the vehicle dynamics of the car. 

There is also a voltage limit placed on the car: 600 V DC. This is also plenty high for your purpose of a small single seater. Unregulated maximum voltages get dangerous fast because it is attractive from a novice designer’s standpoint to examine what happens to electrical efficiencies at high voltages; at a basic level, it looks like increasing voltage to higher levels leads to big advantages. What is very often unknown to the novice is all of the supporting safety devices that need to be around higher and higher voltages. Voltage, in a simple definition, is potential energy. If you improperly direct it (which is frighteningly easy to do), it will forcefully conduct massive amounts of energy at light speeds. Large amounts of energy at light speeds is usually very destructive to humans and leads to very permanent consequences: serious burns, blindness, or death. The limit of 600 V still allows a wide range of designer expression without getting too high. 

*Rule EV.3.3*

### Electrical Components

Here’s some interesting rules about the required electrical components on your EV.

You can use as many electrical motors as you like. We will follow the “simplest is best” rule for the Template Car, but it is within the rules to make a car with one motor per wheel, which is very often done on experienced teams. You could also have 4 motors per wheel if you wanted. 

Any motor on the car must get its power through a Motor Controller. Without diving too deep, a motor controller is a device that changes the Direct Current (DC) electrical energy into a more useful type of electrical energy called “Three-phase Alternating Current”, or “Three-phase AC”. The motor controller is also the device that translates the driver’s accelerator pedal input into a rise or reduction in power that is sent to the motor. 

The rule here is relevant because the organizers are preventing you from connecting the motor straight to the big vehicle battery (the Tractive Battery). You have to have a layer between the battery and the motor, which is the motor controller. 

As you can imagine, the accelerator pedal is very important for controlling the safety of the vehicle. If you find yourself with a faulty accelerator pedal that starts acting like it is stuck in the “max power” position, you’ll have to find something else to slow the car. Usually, a wall. To mitigate this risk, the rules define that we need to use an Accelerator Pedal Position Sensor (or APPS) with certain characteristics and functions so that it is redundant enough to make sure the only time that the motor is commanded to spin is when the driver is actually asking for it to spin. Disclaimer: this still doesn’t guarantee that your driver stays clear of walls. 

In similar fashion, the car will need sensors on the brake pedal and brake system to provide a way for the driver to get out of emergency situations. The rules define that each car needs to have a “Brake Pedal Plausibility Device”, which is a fancy term that means: each car needs a way to determine if the driver is trying to stop, even when the accelerator pedal is being pressed. This means that if the accelerator pedal AND the brake pedal are pressed at the same time, the car should shut off the power. We’ll dive into this device deeper in future sections. 

*EV.4*

### Tractive Battery Care

The big car battery (called the Tractive Battery) that powers the main propulsion motors needs to be removable from your car. There are many rules that define the type of enclosure that your tractive battery can have as well. Protecting the tractive batteries is of highest importance, because the tractive battery is where all the energy is densely packed. So as you design yours, be aware that there will be many many rules surrounding the design that are there to help you get safety right. 

It is mandated at competition that each tractive battery be removed from each car for overnight storage. This is so the organizers can properly zone the risks for the batteries and make sure that no teams interact with their own or other team’s batteries. 

Because the tractive battery needs to be removable from the car, the rules define that it needs to have it’s own transportation cart. This is an extra little push cart that can be forgotten until very late in the year. Best to make it known to you as soon as possible.

*EV.4.10*

### Shutdown Circuit

In order to provide multiple redundant safety checks for the high voltage system (especially when it is active), the organizers have specified rules about a “Shutdown Circuit”. This shutdown circuit is a way to force the car to return to a safe condition if any of the parts or switches in the circuit are opened. The intent is to make it very easy for anyone, be it the driver, team mates, or others, to cut off high voltage power on the vehicle. 

The nature of the Tractive Battery means that it will always be at High Voltage levels. The rules guide the design of the electrical systems on the car so that as the car passes safety checks during its operation, the high voltage energy can travel further and further outside the battery. If the car is safe and in healty condition, the full high voltage path can be traveled, starting at the battery, then to the motor controller, then out to the motor. 

The shutdown circuit involves components that actively monitor the safety of the high voltage connections, as well as exposes emergency stop switches that any operators can push. If anything in the shutdown circuit is tripped, then the car must limit high voltage energy to just the battery, basically cutting it off from the source. As we’ll read about later in the Tech Inspection rules, a team must demonstrate that each part of the shutdown circuit works as intended before the team is allowed to connect their battery to the car at competition. 

The components within the shutdown circuit are:

- A part of the Battery Management System (BMS)
    - This monitors the temperature and voltage of each individual cell in your battery (among other things), and will cut off power if things get too hot/dangerous.
- Insulation Monitoring Device (IMD)
    - This is an electrical device that will monitor your vehicle’s chassis to make sure that it is sufficiently insulated from the high voltage system. If the level of insulation ever gets too low (indicating that High Voltage is starting to creep into your vehicle’s chassis, and thus have the possibility of contacting the driver or team members) then it will cut off power.
- Brake System Plausibility Device (BSPD)
    - We mentioned this one above - it is a way to allow the driver to cut off power if somehow the accelerator gets stuck. The BSPD checks to see if both the accelerator and the brake pedal are pressed at the same time. If so, it will cut off power.
- Interlocks
    - These are parts that allow team members to take off when the car is not allowed to have high voltage. Basically, it is a physical key - if all the interlocks are on the car correctly, then the low voltage electrical system will allow high voltage out of the battery. If not, then the high voltage power will be cut.
- Master Switches
    - These are similar to the interlocks. There are more specific rules about these switches, such as their placement on the car and the stickers and labeling that you must use in order to identify them. This is so anyone can rapidly identify what switches to use in order to shut the car off.
- Shutdown Buttons
    - Similar to the Master Switches, these are big, easily identifiable buttons on the sides of the car and in the cockpit of the car. They are red and must be clearly labeled, for the same reasoning as the Master Switches. In this case, the driver must also have access to a shutdown button within the cockpit so that if other sensors fail, they have an active way to cut off power without needing to exit the vehicle first.
- Brake Over Travel Switch (BOTS)
    - This is an electrical system that must put a little push button behind the brake pedal so that if the vehicle loses brake pressure (like in the event the vehicle’s brake lines get cut during operation), the button will get pushed and the power will get cut off.
- Inertia Switch
    - This electrical sensor measures how quickly the car accelerates in any direction. The intent of this sensor is to be able to sense a crash event. Crashes can be very abrupt, meaning the car goes from moving very fast to moving very slow - this is exactly what the Inertia sensor is meant to measure. If the sensor measures an acceleration high enough, it needs to cut off power, as it is possible that the driver has crashed and is unconscious.

As you can see, there are 8 different devices within the Shutdown Circuit, each monitoring a different risk. All of them have the ability to limit the High Voltage power to just the battery. The Shutdown circuit is very similar to a room that has 8 light switches where the lights only turn on when all 8 switches are on. If any switch gets turned off, then the lights go out. 

*EV.7* 

### The Rest of EV Specifics

The rest of the EV get into deeper detail about the things that your high voltage path needs. Things like what fusing you need, what specific connectors must be used in certain areas, and additional parts on the car that indicate what mode the car is in. The specifics will be necessary if you are designing the electrical system, but it is enough to understand for this overview that there are many detailed rules about what you must include in your electrical system. 

There are also many rules surrounding the electrical work that you can do at the competition, and the procedures you must undergo. We’ll cover those in more detail later in [*Compete in Formula*]({{ "/books/compete-in-formula/" | relative_url }}).
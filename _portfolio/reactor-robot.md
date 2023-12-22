---
title: "Gamma Spectroscopy Robot"
excerpt: "Repair and documentation of a custom-built sample analysis machine for irradiated samples<br/><img src='/images/500x300.png'>"
collection: portfolio
---

In the summer of 2019 until December 2020, I interned at the Rhode Island Nuclear Science Center (RINSC) on the Narragansett Bay Campus. RINSC is home to a variable-output open pool nuclear fission reactor. The reactor core is capable of two main configurations, one high-power (2MW thermal), actively-cooled mode and a lower-power (100KW thermal), passively cooled mode. This is accomplished by rolling the entire core assembly on rails. Primarily utilized in the higher power mode, the lower power mode allows for the use of a dry gamma ray facility outside of the pool. This dry-gamma room is adjacent to the reactor pool walls, and the boronated concrete sides are considerably thinner, to maximize radiation exposure when the core is moved to the low power configuration.
In both configurations, the rabbit system is able to be used. The rabbit system is a pneumatic tube assembly (not unlike what banks used to utilize to transfer cash to customers) that can be used to move capsules (termed `bunnies`) into close proximity to the reactor core.

 During my tenure there, I undertook multiple projects: administration of a research project investigating the dead times of Geiger-Muller detectors, calibration of radioisotope sources for use in facility detector calibration, regular maintenance assistance, and (primarily) the repair and documentation of a custom-built robotics apparatus. RINSC was in possession of two such machines, but only one was functioning. The poor existing documentation and overall complexity of the systems were such that reactor staff only could use the singular functioning machine, as repair had been deemed too difficult.

 Three main components made up these robots:

 1. Electronic Control
 2. Manipulation 
 3. Gamma Spectrometer

 Utilized for biological sample analysis, these robots were custom-built by a company that no longer manufactured them. As such, repair was thought to be too costly to attempt by reactor staff. One customer made significant use of these machines; they manufactured gold-samarium nanoparticles used for delivered drug concentration analysis in tissue samples. Researchers would mix the particles into a drug of interest, and then administer the appropriate dosages to an organic subject (most commonly mice or sheep). The relevant tissue would be excised and delivered to the reactor, who would then run the samples through the rabbit system for a few hours of irradiation. Samples would then be allowed to decay over a week to allow for safe handling by staff in a lead-lined container before processing could commence. Once approximately a week had passed, samples would be removed from storage and inserted into the sample area. From there, a robotic arm capable of 3 degrees of freedom would grab and move each individual sample for measurement on an integrated, shielded gamma spectrometer (to minimize the interference by other samples). An automated computer program would then log each measurement. Due to the large amount of samples run each week, it allowed reactor staff to automate this formerly time-consuming project; with one machine out of order, staff were limited in how many samples they could run. The measurements would be sent back to the researchers; the gold-samarium nanoparticles would emit a recognizable spectra easily resolved from the gamma spectrometer readings. Coupled with the times from irradiation, the total amount of particles could be calculated, allowing researchers to accurately determine how much of their drug made it to the tissue of interest.

### Electronic Control
Without a doubt, the most convoluted part of the setup. These robots were controlled by two distinct PC towers. The primary robot control machine ran MS DOS 6.2 (DOS computer), and was home to the software made to control the behavior of the arm that moved samples between the sample area and the gamma spectrometer (γS). It utilized two separate serial port connections to transfer data to the control board of the robot. All movement was dictated by this machine directly, but it was also connected to the other PC. The secondary PC was running Windows Vista (Vista computer), and had the control software for the gamma spectrometer, which was remotely triggered by the DOS computer whenever a sample was moved over the gamma spectrometer. This trigger was performed by another custom software designed to interface between the γS and DOS computer. 


### Manipulation
Sample manipulation was accomplished by a frame-mounted gantry that utilized screws to manouver in the X,Y, and Z directions. Primary troubleshooting could be done by the use of manual controls integrated into the main control box on the front of the robot, accessed by removing the facade panels. This allowed bugs in the DOS computer control to be eliminated, and was ultimately critical to the identification of the main issue at hand.

### Gamma Spectrometer
Gamma spectroscopy utilized a hyperpure germanium (HPGe) sensor to resolve samples' radioisotope emissions. Critically important to this project, HPGe detectors require cryogenic temperatures to function, and may be damaged by equilibration to room temperature (read: someone forgets to top off the LN_2).
Due to sitting in storage for several years, the detector attached to this machine had run out of liquid nitrogen an unknown amount of times; luckily testing showed that it had not materially damaged the sensors. While permanent damage was not observed, sitting for years without calibration had caused significant drift as identified by the use of a standardized source. As such, calibration of this component was required before full capability was restored.


### Issues and resolution:

Utilizing the manual control mode, several minor hardware issues were identified and resolved in short order:

1. The main X screw was both loose and not properly lubricated, causing skipping and inability to move in the X direction. Retensioning and lubricating the threaded rod amended these issues.
2. Loose cabling was causing connectivity issues; these led to significant positional inaccuracies. I replaced some wire runs that had experienced significant wear - some had been worn by friction between the arm and the gantry to which it was affixed.
3. Reconnection and recalibration of end-of-line stop switches. Due to the aforementioned wiring issues, some of the limit switches were nonfunctional, requiring rewiring and recalibration in the electronic control software.

The primary issue facing the machine was the integrity of data transmission between the DOS machine and the main control board. One of the serial connections on the computer's motherboard was nonfunctional. This was identified by swapping the serial cables; the X direction was serviced by a single cable and the Y/Z dimensions shared the other cable. Swapping the cables resulted in one of the directions not working, which was the described behaviour. As the problem was located on the motherboard, a compatible computer was obtained. Following setup of the custom DOS control software and recalibration of the device, it was able to reach acceptable performance. 


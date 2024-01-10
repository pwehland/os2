                         READ ME file

                   Advanced Micro Devices

Product Name:      AMD PCNET Family NDIS driver
                   for IBM OS/2 2.x and WARP.

Release Date:      June 9, 1995

Product Version:   3.0
-----------------------------------------------------------------------------

                              TABLE OF CONTENTS

This file contains information about AMD AMD PCNET Family
NDIS driver for IBM OS/2 2.x.  It includes the following 
topics:


 1. WHICH AMD ADAPTER DO YOU HAVE?

 2. INSTALLING THE DRIVER

 3. EDITING PROTOCOL.INI TO CHANGE THE CONFIGURATION

 4. THE AMD BULLETIN BOARD

 5. WHO TO CONTACT IF YOU HAVE QUESTIONS

 6. DISKETTE INVENTORY
------------------------------------------------------------------------------


1.  WHICH AMD ADAPTER DO YOU HAVE?
=======================================



2. INSTALLING THE DRIVER
========================

2.1 Installing the driver for IBM LAN Services 2.0   
--------------------------------------------------

To install the AMD driver for IBM LAN Services 2.0 (LAN Requester or 
LAN Server), follow these steps:

 1  Insert the floppy with AMD files into the floppy drive.

 2  Open the LAN Services folder( or run "laps" command from your IBMCOM
    subdirectory).
         
 3  Run OS/2 LAN Services Installation/Configuration.
             
 4  When the Basic or Advanced Installation/Configuration dialog box is 
    displayed, choose Advanced.

 5  When the Install Type dialog box is displayed, choose Install or 
    Configure this workstation.

 6  When the Installation and Configuration dialog box is displayed, choose 
    Configure a component. Then choose OK.
      
 7  When the Configure dialog box is displayed, choose LAN Adapter and 
    Protocol Support and choose Configure. Then choose OK.
          
 8  At the Options dialog box, choose Copy additional network adapter 
    drivers. Then choose OK.
    
 9  At the Copy Additional Network Adapter Drivers dialog box, type the 
    path . Then choose OK.
   
10  When the Copy Diskette dialog box is displayed, choose OK.
            
11  When the Options dialog box is displayed, choose Configure Workstation. 
    Then choose OK.
         
12  When the Configure Workstation dialog box is displayed, remove the 
    current configurations from the Current Configuration list 
    box. 
               
13  Choose the AMD PCNET Family Ethernet Adapter from the Network 
    Adapters list box, by highlighting the entry. Then choose Add to add the 
    AMD to Current Configuration list box.

14  Highlight the appropriate protocols in the Protocols list box. Then 
    choose Add to add them to the Current Configuration list box.

15  Choose the AMD driver at the Current Configuration list box. Then choose 
    Edit. The Parameters for AMD dialog box is displayed.

16  View the default configuration. If the default configuration is 
    appropriate, choose OK.

    If you need to change AMD driver configuration, change the options in 
    this dialog box. 
   
You have finished installing the AMD driver for IBM LAN Services 2.0.



2.2  Installing the driver for IBM Extended Services 1.0 
--------------------------------------------------------

To install the driver for IBM Extended Services 1.0, follow these steps:


 1   Insert the floppy with AMD files into the floppy drive.


 2  Display the Communication Manager main menu and choose Advanced. 

 3  Choose Configuration.

 4  Choose LAN Adapter and Protocol Support (LAPS). 

 5  At the Options dialog box, choose Copy additional network adapter 
    drivers. Then choose OK.
    
 6  At the Copy Additional Network Adapter Drivers dialog box, type the 
    path (a:). Then choose OK.
   
 7  When the Copy Diskette dialog box is displayed, choose OK.
            
 8  When the Options dialog box is displayed, choose Configure Workstation. 
    Then choose OK.
         
 9  When the Configure Workstation dialog box is displayed, remove the 
    current configurations from the Current Configuration list box. 
               
10  Choose the AMD PCNET Family Ethernet Adapter from the Network 
    Adapters list box, by highlighting the entry. Then choose Add to add the 
    AMD to Current Configuration list box.

11  Highlight the appropriate protocols in the Protocols list box. Then 
    choose Add to add them to the Current Configuration list box.

12  Choose the AMD at the Current Configuration list box. Then choose Edit. The 
    Parameters for AMD dialog box is displayed.

14  View the default configuration. If the default configuration is 
    appropriate, choose OK.

    If you need to change AMD's configuration, change the options in 
    this dialog box. 
   
You have finished installing the driver for IBM Extended Services 1.0.



3. EDITING PROTOCOL.INI TO CHANGE THE CONFIGURATION
===================================================

        
To change AMD's configuration, you can edit keyword entries in the 
IRMATR_NIF section of PROTOCOL.INI.  If you are using several AMD adapters, 
you will have [PCNTND_NIF] and [PCNTND2_NIF] sections. Here's a sample 
PCNTND_NIF section in PROTOCOL.INI:

[PCNTND_NIF]
DRIVERNAME=PCNTND$
IOADDRESS=0x300
INTERRUPT=5
DMACHANNEL=9
RXBUFFERS=8
TXBUFFERS=8

For keywords description, please see PCnet Family Network Driver 
Installation Guide.
-----------------------------------------------------------------------



4. THE AMD BULLETIN BOARD
=========================


Set your communications software parameters as follows:

Data:        8
Parity:      N
Stop bits:   1
Speed:       1200, 2400, or 9600 (with V.32)
Emulation:   ANSI or TTY
Number:      (408) 749-4659 9600 baud
Number:      (408) 749-4346 2400 baud


5. WHO TO CONTACT IF YOU HAVE QUESTIONS
=======================================

If you have questions or experience a problem, you can contact AMD
Customer Support. 



6. DISKETTE INVENTORY 
======================

The following files are provided:


File                    Description
--------------          --------------------------------------------------
READ.ME                 This file.

PCNTND.NIF              The network information file that supports 
                        AMD adapters under OS/2 2.0; Extended Services 1.0
                        and LAN Services 2.0.

PCNTND.OS2              The device driver for OS/2 2.0; Extended Services
                        1.0 and LAN Services 2.0.

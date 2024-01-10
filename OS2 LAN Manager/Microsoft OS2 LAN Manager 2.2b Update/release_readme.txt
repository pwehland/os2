

------------------------------------------
LAN Manager 2.2B--Patch to LAN Manager 2.2
------------------------------------------


CONTENTS
========

1.0 Introduction
2.0 LAN Manager 2.2B Patch Installation Instructions
2.1 User Notes
2.2 Bugs Fixed in the LAN Manager 2.2B Release
2.3 Text of Bug Fixes


1.0 INTRODUCTION
================

This release of LAN Manager 2.2B contains all components that have 
been fixed since the original release of LAN Manager 2.2.


2.0 LAN Manager 2.2B Patch Installation Instructions
====================================================

For OS/2
--------

1. Type NET STOP WKSTA at an OS/2 command prompt.
2. Detach LAN Manager using the LAN Manager Setup utility on the
   hard disk.
3. Reboot the system.
4. Once the system has rebooted, insert LAN Manager 2.2B OS/2 Patch 
   Disk 1 into the floppy drive.
5. At an OS/2 command prompt, change to that floppy drive (that is, 
   A: or B:) and type SETUP.
6. Follow the instructions given on the screen.

For MS-DOS
----------

1. Insert LAN Manager 2.2B DOS Patch Disk 1 into the floppy drive.
2. At an MS-DOS command prompt, change to that floppy drive (that is,
   A: or B:) and type SETUP.
3. Follow the instructions given on the screen.


2.1 User Notes
--------------

Note One: Problem Loading LM 2.2b NETWKSTA.EXE into MS-DOS 6.2 UMBs
-------------------------------------------------------------------

When you install the LAN Manager 2.2b Patch onto MS-DOS 6.2, the 
NETWKSTA.EXE is not correctly loaded into the upper memory blocks 
(UMBs) because LAN Manager initialization incorrectly processes the 
version number of MS-DOS 6.2. 

Make sure that there is adequate contiguous UMB space to accommodate 
the redirector. Do not load SMARTDRV or other drivers and utilities 
into the UMB prior to starting the workstation. Many personal 
computers have UMB space available in the E000 segment (verify that 
ROM and shared memory devices are not located in this region). To make 
this memory region available use I=E000-EFFF as an option for 
EMM386.EXE in CONFIG.SYS. If you do not need expanded memory (EMS) use 
NOEMS as an EMM386.EXE option to save the 64k page frame for EMS 
support.

Example line in CONFIG.SYS

    Device=C:\WINDOWS\EMM386.EXE NOEMS I=E000-EFFF

Microsoft has confirmed this to be a problem and is testing a possible 
fix. Contact Microsoft Product Support Services for its status and 
availability. New information will be posted in the Microsoft 
Knowledge Base as it becomes available.


Note Two: MS-DOS Low Density Install Diskettes not Available.
-------------------------------------------------------------

The low density MS-DOS client patch install diskettes are not 
available.

Here is a procedure for installing the Patch on a network workstation 
with a 360k floppy drive(s).

1. NET SHARE a directory on a network file server.
2. Copy all files on the LAN Manager 2.2b MS-DOS Patch high density 
   disk to the shared directory.
3. Connect to this share from the workstation that you want to 
   upgrade with the NET USE command.
4. Apply the patch to the workstation by running SETUP.EXE from the 
   shared directory.


Note Three: OS/2 Drivers and Files Included with Patch.
-------------------------------------------------------

Updated versions of the following OS/2 files are included with this 
patch:

 - PMSPL.DLL
 - PSCRIPT.DRV
 - PMSPL.EXE
 - OS2KRNL

These files are not automatically installed. To install these files on 
a OS/2 computer you must manually decompress and replace them.  Use 
the command DECOMP to decompress the files. Use File Manager to change 
attributes, rename, and copy over these files.

For an example, following are the steps to replace OS2KRNL:

1. Decompress the file using the command DECOMP.
2. Open File Manager.
3. Choose View, then Include, then File Flags. Select Show Read-Only, 
   Archive, Hidden, and Other.
4. Choose the C: drive, then highlight OS2KRNL.
5. Choose File, Change Flags, deselect the Read Only, Archive, Hidden, 
   and System flags, and click on Change.
6. Rename the file OS2KRNL to OS2KRNL.OLD.
7. Copy the new OS2KRNL from the floppy disk, and highlight it in File
   Manager.
8. Choose File, then choose Change Flags. Select the Read Only, 
   Archive, Hidden, and System flags, then click on Change.

The following third party manufacturer's .BID drivers are also 
supplied with this patch: 

- Adaptec 174x
- CPQC710 
- Ultra24f

They are installed as above.

These drivers are manufactured by third party vendors independent of 
Microsoft; we make no warranty, implied or otherwise regarding these 
drivers' performance or reliability


2.2 Bugs Fixed in the LAN Manager 2.2B Release
==============================================

 - Printsta Fails, Hangs MS-DOS Workstation When Printscreen Starts
 - More Than 32 Domain Controllers on a Domain Causes PDC GP Fault
 - Ill-Formed SMB From Client Causes Server to Die or GP Fault
 - Workstation Hangs After Period of Copying or Running HLAPI Code
 - Net Logon on MS-DOS Client Not Validated by Server
 - Attempt to Stop/Restart PDC Locks out BDC if No One Logged On
 - WinAdmin Creates Too Many ACL Entries, Making NET.ACC Too Big
 - FAT Server Stops Responding if Same Byte Range Repeatedly Locked
 - Replicator Copies Files Already in Sync or for HPFS386 Importer
 - API Call Holds Semaphores After Access Check on Non-Existent File
 - Later Logon Scripts Fail After Time-out Occurs When Logon Running
 - BACKACC Failure from AT Command Required Server Stop/Restart
 - NetBEUI Needs SRB On/Off Switch with 3Com NetBuilder SRT Bridge
 - FTBOOT Causes Trap D/Trap C When Recovering Boot Volume Mirror
 - Core Drive Error Causes Multiple Errors and Data Corruption
 - Failure of Network Request During Logon Hangs Time-out Period
 - MS-DOS Enhanced Workstation Runs Out of Netbufs and Hangs
 - File Seek Fails After Buffer Flushing Error on Seek Initiation
 - Net Password Command During Sync Deadlocks Server and Netlogon
 - WS Hangs Running TCP/IP, DLC and Windows Enh on IBM Token Ring
 - WfW Workstation Cannot Run FoxPro after a LM Workstation Does
 - Application Produces Occasional NET808 and NET805 Errors
 - Windows NetBIOS App Encounters SYS3175 Trap Under OS/2 2.0
 - System Hangs or Reboots Accessing File on Disconnected Drive
 - NET LOGOFF /Y Returns NET2402 if Files Open on a Connection
 - NETWKSTA.EXE Won't Run with MS-DOS 6.0 Without SETVER
 - Password Displayed in Share Info Dialog when Server Share-level
 - More than 300 Entries in RPL.MAP Causes RPLMGR to Trap 000d
 - NET STOP RDR /Y Followed by NET START RDR Hangs MS-DOS Client
 - Period ( . ) Not a Valid Character in Workstation Names
 - Logon Starts Failing after 16 Logons with a Logon Script
 - Running Local and Remote I/O Stress Tests Caused GP Fault
 - DosPeekNmPipe Call Returns Too Much Data, Causes Broken Pipe
 - SQL Queries Under RAS Cause Lock-up, Reboot or EMM Exception #06
 - Full Sync Initiated by Small Netlogon Service Buffer Request
 - LM Setup Does Not Recognize IBM DOS 5.02 as Valid DOS Version
 - Netlogon Service Encounters GP Fault as Array Memory is Overrun
 - DOSPeekNmPipe API Returns Incorrect Byte Count for Its Buffer
 - Issuing CTRL-C as BACKACC Writes to Hard Disk Causes GP Fault
 - OS/2 Server Hangs if Network Adapter Cannot Reset
 - Duplicate Name and Net Address on Token Ring Crashes Server
 - MS-DOS Applications Incorrectly Report "0 Bytes Free"
 - RESTACC Fails with "SYS0111 File Name Too Long" Error
 - Badly Formed Server Message Block Sent to Server Causes Trap
 - Netlogon Performs Continuous Full Synchronization
 - UPS Service Fails Compaq ProSignia if Low Battery Signal Enabled
 - Windows Hangs or Crashes to MS-DOS Prompt If Running Many Apps
 - Workstation Hangs with NET 805, Server Records Incomplete NCB Error
 - Trap D Occurs With HPFS386 when ATTRIB *.TXT /S is Entered
 - Trap D in TCPNB$
 - DOS TCP/IP Clients get Logged on Standalone Despite DC Responses
 - TCP/IP Server Won't Send Datagrams; BDCs Go Out of Sync
 - BCASTADDR Parameter in PROTOCOL.INI Ignored by OS/2 TCP/IP
 - All TCP/IP Servers on Net Trap in NBDRV.0S2
 - Server Crashes and Issues TRAP 0003
 - Sybase Server Doesn't Respond to TCP/IP "Cancel" Commands
 - TCP/IP MS-DOS Utilities Cannot Connect with IBM 3090 MVS
 - Information Packets Incorrectly Reassembled After Crossing Router
 - TCP/IP Returns Wrong Error Code on Failed Call
 - LM Server Trap D's in TCPDRV When Sent LLC XID
 - TCP/IP Server Routes Traffic from Token Ring to Ethernet, Crashes
 - Error 53--TCPCONNECTIONS Depleted, Connection Denied to Client


2.3 Text of Bug Fixes
---------------------

----------------------------------------------------------------
Printsta Fails, Hangs MS-DOS Workstation When Printscreen Starts
----------------------------------------------------------------

CSD:  LM22.CSD01.037

SYMPTOMS
========

Printsta failed. If the user on an MS-DOS workstation attempted to 
perform print screen operations, the workstation operated properly 
until printscreen was initiated, then would hang.

RESOLUTION
==========

The timer stack was getting corrupted, so the size of the stack was 
increased. Also, some of the retry logic was changed so that on slow 
PCs requests no longer time out.

Binary Affected
---------------

PRINTSTA.EXE


---------------------------------------------------------------
More Than 32 Domain Controllers on a Domain Causes PDC GP Fault
---------------------------------------------------------------

CSD:  LM22.CSD01.040

SYMPTOMS
========

The addition of more than 32 domain controllers (primary and backup) 
on a domain caused a GP Fault on the primary domain controller.

RESOLUTION
==========

The number of combined members (backup and primary domain controllers) 
allowed in a domain was changed from 32 to 128. A check was also added 
that keeps the primary domain controller from faulting if more than 
128 domain controllers are added to the domain (although an error 
still is logged).

Binary Affected
---------------

NETLOGON.EXE
NETAPI.DLL


-----------------------------------------------------------
Ill-Formed SMB From Client Causes Server to Die or GP Fault
-----------------------------------------------------------

CSD:  LM22.CSD01.041

SYMPTOMS
========

An ill-formed server message block from a client sometimes caused the 
server to either GP fault or "go dead."

RESOLUTION
==========

The manner in which ill-formed server message blocks are handled was 
changed. Specifically, code was added that put a null at the end of 
their truncated or corrupted strings.

Binary Affected
---------------

HPFS386.IFS
HPFS.386


---------------------------------------------------------------
Workstation Hangs After Period of Copying or Running HLAPI Code
---------------------------------------------------------------

CSD:  LM22.CSD01.042

SYMPTOMS
========

After 15 minutes of activity such as copying files between a server 
and a workstation or running Attachmate HLAPI code that polls the 
server, the workstation would hang.

RESOLUTION
==========

The MS-DOS redirector stack was overflowing. Stack size was increased.

Binary Affected
---------------

NETWKSTA.500
NETWKSTA.401
NETWKSTA.330


--------------------------------------------------
Net Logon on MS-DOS Client Not Validated by Server
--------------------------------------------------

CSD:  LM22.CSD01.043

SYMPTOMS
========

A net logon on an MS-DOS client sometimes resulted in a standalone 
logon--the server refused to validate it.

RESOLUTION
==========

If the name-query packet was larger than usual (that is, if an 
additional field in the resource record was filled in) then a routine 
in TINYRFC.EXE failed to free a buffer. The code was modified to 
assure that the buffer is freed.

Binary Affected
---------------

TINYRFC.EXE


-------------------------------------------------------------
Attempt to Stop/Restart PDC Locks out BDC if No One Logged On
-------------------------------------------------------------

CSD:  LM22.CSD01.044

SYMPTOMS
========

When no one was logged on at the backup domain controller and the 
primary domain controller was stopped and started, the backup 
attempted to connect to the primary using its computer name and some 
unknown password. This repeated, causing two effects: 

 - the account was locked out (if lockout was set up)

 - the audit log was filled with spurious bad password attempts

Netlogon synchronization was not affected.

RESOLUTION
==========

Code was changed so that a backup domain controller no longer attempts 
a single API if there is no one logged on: it simply gets the next 
request. This does not lessen functionality, as these calls would fail 
in any case, but it makes the failures local so they are not logged.

Binary Affected
---------------

NETLOGON.EXE


-------------------------------------------------------------
WinAdmin Creates Too Many ACL Entries, Making NET.ACC Too Big
-------------------------------------------------------------

CSD:  LM22.CSD00.002

SYMPTOMS
========

WinAdmin's "permit tree" feature incorrectly walked the directory tree 
and created ACL entries for each file and for its subdirectory,
 quickly causing NET.ACC to become huge.

RESOLUTION
==========

Code was changed to create ACL entries only for subdirectories and to 
delete any existing ACL entries for files. The change also displays
both explicit and inherited permissions.

Binary Affected
---------------

NETADMIN.EXE


----------------------------------------------------------------
FAT Server Stops Responding if Same Byte Range Repeatedly Locked
----------------------------------------------------------------

CSD:  LM22.CSD00.003

SYMPTOMS
========

When the same byte-range was repeatedly locked, a FAT server stopped 
responding after some number of lock attempts.

RESOLUTION
==========

Code was changed to correct time-out determination.

Binary Affected
---------------

NETSERVR.EXE


---------------------------------------------------------------
Replicator Copies Files Already in Sync or for HPFS386 Importer
---------------------------------------------------------------

CSD:  LM22.CSD00.004

SYMPTOMS
========

The replicator copied files already in sync from subdirectories that 
contained large numbers of files, and when the importer had an HPFS386 
disk.

RESOLUTION
==========

A larger buffer size was implemented in the replicator code.

Binary Affected
---------------

REPLCLI.EXE


-----------------------------------------------------------------
API Call Holds Semaphores After Access Check on Non-Existent File
-----------------------------------------------------------------

CSD:  LM22.CSD00.005

SYMPTOMS
========

Checking the access on a file that did not exist (on a FAT partition) 
caused the API call to take but not release three semaphores.

RESOLUTION
===========

Code was changed so that it now sets the correct error and frees the 
semaphores before returning.

Binary Affected
---------------

NETAPI.DLL


-----------------------------------------------------------------
Later Logon Scripts Fail After Time-out Occurs When Logon Running
-----------------------------------------------------------------

CSD:  LM22.CSD00.006

SYMPTOMS
========

If a Windows logon script was still running when the logon script 
time-out occurred, all subsequent logon scripts failed until Windows 
was exited.

RESOLUTION
==========

A variable that checks the time-out in a DLL was set to initialize 
each time the routine is called.

Binary Affected
---------------

NETAPI.DLL (Win16 version)


------------------------------------------------------------
BACKACC Failure from AT Command Required Server Stop/Restart
------------------------------------------------------------

CSD:  LM22.CSD00.007

SYMPTOMS
========

BACKACC failed to complete when run from the AT command, and could not 
be run by AT again until the server was stopped and started.

RESOLUTION
==========

The server had too many open files, since remote APIs were not closing 
the UASCHG.LOG file once it was opened. Code was changed to close this 
file after each open.


Binary Affected
---------------

NETAPI.DLL


---------------------------------------------------------------
NetBEUI Needs SRB On/Off Switch with 3Com NetBuilder SRT Bridge
---------------------------------------------------------------

CSD:  LM22.CSD00.008

SYMPTOMS
========

With the 3Com NetBuilder SRT Bridge, NetBEUI required a switch to turn 
instant flipping of the source routing bit on and off.

RESOLUTION
==========

Added [NETBEUI_XIF] parameter, LocalRing, which is 0 by default. When 
this is zero, the source routing bit is turned on immediately. When it 
is 1, it allows the packet to traverse the local ring three times 
before the SRB is turned on.

Binary Affected
---------------

NETBEUI.*


--------------------------------------------------------------
FTBOOT Causes Trap D/Trap C When Recovering Boot Volume Mirror
--------------------------------------------------------------

CSD:  LM22.CSD00.010

SYMPTOMS
========

FTBOOT caused a Trap D or Trap C when trying to recover the boot 
volume mirror.

RESOLUTION
==========

Code was changed to clear the extended partition record if the boot 
volume mirror is the only partition on its disk.

Binary Affected
---------------

FTBOOT.EXE


-----------------------------------------------------------
Core Drive Error Causes Multiple Errors and Data Corruption
-----------------------------------------------------------

CSD:  LM22.CSD00.011

SYMPTOMS
========

The core drive issued an error code which the BID handled incorrectly, 
causing multiple errors and data corruption. This affected other SCSI 
drives attached to an IBM SCSI adapter, not just the core drives.

RESOLUTION
==========

This was fixed by causing the BID to set a timer and simulate an 
interrupt, which allows it to handle the error condition correctly.

Binary Affected
---------------

ABIOS.BID


-------------------------------------------------------------
Failure of Network Request During Logon Hangs Time-out Period
-------------------------------------------------------------

CSD:  LM22.CSD00.012

SYMPTOMS
========

In Windows, failure of a network request during a logon attempt (such 
as attempting to connect to a down server) caused the time-out period 
to hang for an excessively long time.

RESOLUTION
==========

Changed the logic to use a count to check for the elapsed time since 
the dialog was started and to abort the logon script based on this.

Binary Affected
---------------

NETAPI.DLL (Win16 version)


---------------------------------------------------------
MS-DOS Enhanced Workstation Runs Out of Netbufs and Hangs
---------------------------------------------------------

CSD:  LM22.CSD00.014

SYMPTOMS
========

MS-DOS enhanced workstations would run out of netbufs and hang. 

RESOLUTION
==========

Code was changed so that the terminating loop case no longer became 
incorrect. The MS-DOS redirector is now guaranteed not to run out of 
work buffers.

Binary Affected
---------------

NETWKSTA.500
NETWKSTA.401
NETWKSTA.330


--------------------------------------------------------------
File Seek Fails After Buffer Flushing Error on Seek Initiation
--------------------------------------------------------------

CSD:  LM22.CSD00.015

SYMPTOMS
========

File seeks failed if there was an error flushing a buffer when the 
seek was initiated. 

RESOLUTION
==========

This was fixed by correcting the stack manipulation.

Binary Affected
---------------

NETWKSTA.500
NETWKSTA.401
NETWKSTA.330


--------------------------------------------------------------
Net Password Command During Sync Deadlocks Server and Netlogon
--------------------------------------------------------------

CSD:  LM22.CSD00.016

SYMPTOMS
========

Issuance of a net password command while a domain controller (backup 
or primary) was performing a full sync caused a deadlock that kept 
part of the server and part of Netlogon from functioning. Domain 
controllers made no progress syncing, the net password command stopped 
functioning, and the Netlogon process that gets and responds to 
requests would hang.

RESOLUTION
==========

The code was changed to fix the logic code so that the Netlogon 
process releases its semaphore before requesting the server's 
semaphore.

Binary Affected
---------------

NETAPI.DLL


--------------------------------------------------------------
WS Hangs Running TCP/IP, DLC and Windows Enh on IBM Token Ring
--------------------------------------------------------------

CSD:  LM22.CSD00.017

SYMPTOMS
========

Workstations running TCP/IP, DLC, and Windows Enhanced mode with an 
IBM token ring card would randomly hang.

RESOLUTION
==========

The stack usage of the token ring driver was changed to alleviate the 
problem.

Binary Affected
---------------

IBMTOK.DOS


-----------------------------------------------------------
WfW Workstation Cannot Run FoxPro after LM Workstation Does
-----------------------------------------------------------

CSD:  LM22.CSD00.018

SYMPTOMS
========

When a LAN Manager workstation was running a FoxPro application on a 
LAN Manager server, a Windows for Workgroups workstation that tried to 
run the FoxPro application received:

   Network Error Reading Drive X:

followed by:

   File Read Error

When a Windows for Workgroups workstation initialized the FoxPro 
application with a database file 2K or larger, both the first and the 
second workstations received the error messages.

RESOLUTION
==========

The FAT file server was changed so that it now correctly sets two 
fields in a server message block sent to the Windows for Workgroups 
client.

Binary Affected
---------------

NETSERVR.EXE


--------------------------------------------------------
Application Produces Occasional NET808 and NET805 Errors
--------------------------------------------------------

CSD:  LM22.CSD00.019

SYMPTOMS
========

An application produced occasional NET808 and NET805 errors during 
command processing.

RESOLUTION
==========

Buffer flushing code was changed to correct this.

Binary Affected
---------------

NETWKSTA.500
NETWKSTA.401
NETWKSTA.330


----------------------------------------------------------
Windows NetBIOS App Encounters SYS3175 Trap Under OS/2 2.0
----------------------------------------------------------

CSD:  LM22.CSD00.020

SYMPTOMS
========

A Windows NetBIOS application encountered a SYS3175 trap while issuing 
a listen. The application worked correctly under Win 3.1 but not in 
the Win 3.1 environment under OS/2 2.0.

RESOLUTION
==========

OS/2 was not handling the call correctly. A workaround was implemented 
in NETVDD.

Binary Affected
---------------

NETVDD.SYS


------------------------------------------------------------
System Hangs or Reboots Accessing File on Disconnected Drive
------------------------------------------------------------

CSD:  LM22.CSD00.021

SYMPTOMS
========

The system would hang or reboot when trying to access a file in a 
Windows application on a disconnected drive when Windows was being run 
over the net, usually in a token ring environment.

RESOLUTION
==========

The program was running out of network buffers. Code was changed to 
add checks to the code path that retrieves buffers.

Binary Affected
---------------

NETWKSTA.500
NETWKSTA.401
NETWKSTA.330


-----------------------------------------------------------
NET LOGOFF /Y Returns NET2402 if Files Open on a Connection
-----------------------------------------------------------

CSD:  LM22.CSD00.022

SYMPTOMS
========

The command NET LOGOFF /Y returned the error NET2402 if files were 
open on a connection. Subsequent attempts returned the same error.

RESOLUTION
==========

The system file table entry is now marked as invalid, allowing the 
command to complete. Applications receive an error if they try to 
access an open file's handle.

Binary Affected
---------------

NETWKSTA.500
NETWKSTA.401
NETWKSTA.330


-----------------------------------------------------
NETWKSTA.EXE Won't Run with MS-DOS 6.0 Without SETVER
-----------------------------------------------------

CSD:  LM22.CSD00.024

SYMPTOMS
========

NETWKSTA required the use of SETVER to run with MS-DOS 6.0. 

RESOLUTION
==========

Code was changed. NETWKSTA now allows MS-DOS 6.0.

Binary Affected
---------------

NETWKSTA.500
NETWKSTA.401
NETWKSTA.330


---------------------------------------------------------------
Password Displayed in Share Info Dialog when Server Share-level
---------------------------------------------------------------

CSD:  LM22.CSD00.026

SYMPTOMS
========

Password is displayed in share info dialog when server is share-level.

RESOLUTION
==========

This has been corrected so that a read-only clear-text share password 
is displayed if the server is share-level. If you choose OK without 
changing anything, the system deletes the password on the share, 
leaving it blank.

Binary Affected
---------------

NETADMIN.EXE


-----------------------------------------------------------
More than 300 Entries in RPL.MAP Causes RPLMGR to Trap 000d
-----------------------------------------------------------

CSD:  LM22.CSD00.027

SYMPTOMS
========

If the RPL.MAP file had more than 300 entries, RPLMGR issued Trap 000d 
on startup. After a workstation beyond number 300 was added, 
refreshing the workstation list or exiting and re-entering RPLMGR 
caused the program to Trap 000d.

Session Title:
RPLMGR.EXE

    SYS1943:A program caused a protection violation.
    TRAP 000D
    AX=0296  BX=EAF0  CX=0000  DX=1BF7  BP=1D90
    SI=052A  DI=0000  DS=1957  ES=1BCF  FLG=2212
    CS=18F7  IP=07D8  SS=01C7  SP=1D8A  MSW=001B
    CSLIM=07F2  SSLIM=1FFF  DSLIM=0CEF  ESLIM=F019
    CSACC=FB  SSACC=F3  DSACC=F3  ESACC=F3
    ERRCD=0000 ERLIM=****  ERACC=**

RESOLUTION
==========

Memory re-allocation code was modified so that the size of the memory 
block now is calculated correctly.

Binary Affected
---------------

RPLMGR.DLL


-------------------------------------------------------------
NET STOP RDR /Y Followed by NET START RDR Hangs MS-DOS Client
-------------------------------------------------------------

CSD:  LM22.CSD00.030

SYMPTOMS
========

Performing NET STOP RDR /Y followed by NET START RDR sometimes hung 
an MS-DOS client or caused it to hang a few seconds after returning 
from the commands.

RESOLUTION
==========

Code was changed to handle cases wherein no protocols are loaded and 
the network card NDIS driver is sending a packet up to the protocol.

Binary Affected
---------------

PROTMAN.DOS
PROTMAN.EXE


-------------------------------------------------------
Period ( . ) Not a Valid Character in Workstation Names
-------------------------------------------------------

CSD:  LM22.CSD00.031

SYMPTOMS
========

Workstation names could not include '.' as a character. 

RESOLUTION
===========

The list of valid characters for workstation names was changed to 
include the period ( . ).

Binary Affected
---------------

NETADMIN.EXE


--------------------------------------------------------
Logon Starts Failing after 16 Logons with a Logon Script
--------------------------------------------------------

CSD:  LM22.CSD00.037

SYMPTOMS
========

Under Windows, logging in and out with a logon script 16 times in a 
row caused the logon to start failing. 

RESOLUTION
==========

The LMSCRIPT.$$$ flag file was being left open after logon script 
processing, so that after about 16 logons too many files were open. 
Changes in code cause the file to be closed now before it is deleted.

Binary Affected
---------------

NETAPI.DLL


---------------------------------------------------------
Running Local and Remote I/O Stress Tests Caused GP Fault
---------------------------------------------------------

CSD:  LM22.CSD00.038

SYMPTOMS
========

Running a local and a remote I/O stress test simultaneously caused a 
GP fault.

RESOLUTION
==========

Code was changed to allow HPFS386 and the LM OS/2 redirector to share 
a field in a common structure.

Binary Affected
---------------

NETWKSTA.SYS


------------------------------------------------------------
DosPeekNmPipe Call Returns Too Much Data, Causes Broken Pipe
------------------------------------------------------------

CSD:  LM22.CSD00.040

SYMPTOMS
========

The OS/2 redirector returned more data than an MS-DOS client machine 
could handle in response to a DosPeekNmPipe call. The underlying 
transport returned error 06h (Incomplete Received Message) to the 
MS-DOS redirector on a RECEIVE ANY, causing it to hang the session and 
result in a broken pipe.

RESOLUTION
==========

Code was changed to correct circular buffer handling.

Binary Affected
---------------

NETWKSTA.SYS


----------------------------------------------------------------
SQL Queries Under RAS Cause Lock-up, Reboot or EMM Exception #06
----------------------------------------------------------------

CSD:  LM22.CSD00.041

SYMPTOMS
========

During SQL queries under RAS the machine would occasionally lock-up, 
reboot, or report EMM Exception #06.

RESOLUTION
==========

The redirector's internal critical stacks were too small and were 
getting overrun when RAS would back up NCB processing. The stacks were 
amended to alleviate the problem.

Binary Affected
---------------

NETWKSTA.500
NETWKSTA.401
NETWKSTA.330


------------------------------------------------------------
Full Sync Initiated by Small Netlogon Service Buffer Request
------------------------------------------------------------

CSD:  LM22.CSD00.042

SYMPTOMS
========

For groups with large numbers of users, the Netlogon service was not 
asking for a buffer large enough to contain all users, resulting in a 
full sync between domain controllers.

RESOLUTION
==========

A larger buffer has been allocated for this request.

Binary Affected
---------------

NETLOGON.EXE


-------------------------------------------------------------
LM Setup Does Not Recognize IBM DOS 5.02 as Valid DOS Version
-------------------------------------------------------------

CSD:  LM22.CSD00.044

SYMPTOMS
========

The LAN Manager Setup program did not recognize IBM DOS 5.02 as a 
valid DOS version.

RESOLUTION
==========

Checks were added for this DOS version.

Binary Affected
---------------

SETUP.EXE


---------------------------------------------------------------
Netlogon Service Encounters GP Fault as Array Memory is Overrun
---------------------------------------------------------------

CSD:  LM22.CSD00.045

SYMPTOMS
========

The Netlogon Service was ending in a GP fault when memory usage for an 
array was overrun.

RESOLUTION
==========

Larger allocations were made for the array.

Binary Affected
---------------

NETLOGON.EXE
NETAPI.DLL


-------------------------------------------------------------
DOSPeekNmPipe API Returns Incorrect Byte Count for Its Buffer
-------------------------------------------------------------

CSD:  LM22.CSD00.046

SYMPTOMS
========

The DOSPeekNmPipe API returned an incorrect count for the number of 
bytes in its buffer. 

RESOLUTION
==========

This was caused when the DOSPeekNmPipe API did not initialize 
correctly under certain circumstances. It has been changed so that it 
now initializes the number of bytes read to the correct value.

Binary Affected
---------------

NETWKSTA.500
NETWKSTA.401
NETWKSTA.330


-------------------------------------------------------------
Issuing CTRL-C as BACKACC Writes to Hard Disk Causes GP Fault
-------------------------------------------------------------

CSD:  LM22.CSD00.047

SYMPTOMS
========

Issuing CTRL-C as BACKACC was writing to the hard disk caused a GP 
fault.

RESOLUTION
==========

The signal handler was changed so that it now correctly releases 
semaphores. 

Binary Affected
---------------

BACKACC.EXE


-------------------------------------------------
OS/2 Server Hangs if Network Adapter Cannot Reset
-------------------------------------------------

CSD:  LM22.CSD00.048

SYMPTOMS
========

COMTOKR.OS2 went into a tight loop if the network adapter was in a 
state where it would not reset, causing the OS/2 server to hang.

RESOLUTION
==========

The driver was checking an incorrect flag. Code was changed so that it 
now checks the correct one.

Binary Affected
---------------

COMTOKR.OS2


------------------------------------------------------------
Duplicate Name and Net Address on Token Ring Crash Server
------------------------------------------------------------

CSD:  LM22.CSD00.049

SYMPTOMS
========

A server would crash if it had the same NetBIOS name, local session 
number and locally administered net address as a workstation on the 
network.

RESOLUTION
==========

Since incorrectly administered workstations can cause problems on the 
network, the fix centered on detecting this situation and causing the 
offending workstation to hang. 

Binary Affected
---------------

NETBEUI.EXE
NETBEUI.OS2


-----------------------------------------------------
MS-DOS Applications Incorrectly Report "0 Bytes Free"
-----------------------------------------------------

CSD:  LM22.CSD00.050

SYMPTOMS
========

On server drive geometries exceeding 2 GB, MS-DOS applications would 
report that there was no free space left on the disk, or "0 bytes 
free."

RESOLUTION
==========

MS-DOS applications (such as DIR) do 16-bit multiplication to 
determine the free space on the server disk, and on server drive 
geometries exceeding 2 GB the cluster size becomes to big to be 
contained in a 16-bit number. Checks were installed to prevent 
returning more information to MS-DOS clients than can fit into a 16-
bit number.

Binary Affected
---------------

HPFS.386


-----------------------------------------------------
RESTACC Fails with "SYS0111 File Name Too Long" Error
-----------------------------------------------------

CSD:  LM22.CSD00.052

SYMPTOMS
========

RESTACC failed with a "SYS0111 File Name Too Long" error under the 
following circumstances:

 - net access c:\data /a /f:all /s:write;delete;acl

 - net access c:\data /a /f:acl /s:write;delete

 - net access c:\data /a /f:acl;delete /s:write

 - net access c:\data /a /f:acl;delete;write /s:all

followed by:

backacc c: /s
restacc c: /s

RESOLUTION
==========

The method by which the size of the structure is determined has been 
changed.

Binary Affected
---------------

NETAPI.DLL


------------------------------------------------------------
Badly Formed Server Message Block Sent to Server Causes Trap
------------------------------------------------------------

CSD:  LM22.CSD00.053

SYMPTOMS
========

A badly formatted server message block sent to the server, caused the 
following trap:

Trap 000D
AX=0000  BX =0FF6  CX=0002  DX=0001  BP=EEF2
SI=D2C4  DI=9BEA  DS=0658  ES=0658  FLG=2202
CS=0908  IP=174C  SS=0038  SP=EEAC  MSW=001B
CSLIM=370B  SSLIM=EB85  DSLIM=FFFF  ESLIM=FFFF
CSACC=9B  SSACC=97  DSACC=93  ESACC=93

RESOLUTION
==========

The method by which the size of the incoming server message block is 
determined has been made more robust.

Binary Affected
---------------

HPFS.386


-------------------------------------------------
Netlogon Performs Continuous Full Synchronization
-------------------------------------------------

CSD:  LM22.CSD00.054

SYMPTOMS
========

If a backup domain controller failed to set its password (which causes 
a new attempt to do so every 15 minutes) and a full sync took longer 
than 15 minutes, Netlogon performed a continuous full sync.

RESOLUTION
==========

A check was installed to make sure that a request to change the backup 
domain controller password is not dealt with during a user-accounts 
system update.

Binary Affected
---------------

NETLOGON.EXE


----------------------------------------------------------------
UPS Service Fails Compaq ProSignia if Low Battery Signal Enabled
----------------------------------------------------------------

CSD:  LM22.CSD00.060

SYMPTOMS
========

Uninterruptible power supply (UPS) service failed when connected to 
the serial port of a Compaq ProSignia running Microsoft LAN Manager 
2.1 or 2.1a and the low battery signal check was enabled in 
LANMAN.INI. The server shut down during initialization even under 
normal UPS operation, usually when the UPS service was started.

RESOLUTION
==========

Timing conditions were changed so that the UPS service does not fail 
with high speed machines.

Binary Affected
---------------

UPSDRV.OS2
UPS.EXE


--------------------------------------------------------------
Windows Hangs or Crashes to MS-DOS Prompt If Running Many Apps
--------------------------------------------------------------

CSD:  LM22.CSD00.061

SYMPTOMS
========

On a very low memory Windows 3.1 machine, with both Windows 3.1 and 
Windows applications running off of a server on the net, loading many 
applications caused Windows to hang or to crash to an MS-DOS prompt 
when pulling up print dialog boxes or exiting applications.

RESOLUTION
==========

Two instructions that prevent page faults (which invalidate the stack) 
from occurring in Windows have been reversed in order so that they now 
function more effectively.

Binary Affected
---------------

NETWKSTA.500
NETWKSTA.401
NETWKSTA.330


-------------------------------------------------------------------
Workstation Hangs with NET 805, Server Records Incomplete NCB Error
-------------------------------------------------------------------

CSD:  LM22.CSD00.062

SYMPTOMS
========

A custom named pipes program, when performing raw block write 
commands, would cause the workstation to hang with a NET 805 error. 
The server would also record a NetBIOS "Incomplete NCB Error" message.

RESOLUTION
==========

Code was changed to check that the pipe was not in a closing state 
before performing the operation.

Binary Affected
---------------

NETWKSTA.SYS


----------------------------------------------------------
Trap D Occurs With HPFS386 when ATTRIB *.TXT /S is Entered
----------------------------------------------------------

CSD:  LM22.CSD00.063

SYMPTOMS
========

A TRAP D would occur with HPFS386 when the user typed ATTRIB *.TXT /S 
at the root of a large (greater than 1 GB) partition with a huge tree 
structure.

RESOLUTION
==========

An invalid instruction has been changed.

Binary Affected
---------------

HPFS.386


----------------
Trap D in TCPNB$
----------------

SYMPTOMS
========

The following trap screen would be displayed on the server:

TRAP: 000D

AX=17FE BX=4B54 CX=02CA DX=0000 BP=0744
SI=0000 DI=0E18 DS=0D80 ES=0D80 FLG=2202
CS=0DF0 IP=2716 SS=1920 SP=073C MSW=001B
CSLIM=9850 SSLIM=07FF DSLIM=417A ESLIM=417A
CSACC=9B SSACC=93 DSACC=93 ESACC=93
ERRCD=000 ERLIM=**** ERACC=**
Exception in device driver: TCPNB$

The system detected an internal processing error at location 0228:37CD

RESOLUTION
==========

An invalid instruction has been changed.

Binary Affected
---------------

NBDRV.OS2


----------------------------------------------------------------
DOS TCP/IP Clients get Logged on Standalone Despite DC Responses
----------------------------------------------------------------

SYMPTOMS
========

Occasionally workstations using the TCP/IP protocol stack would be 
logged on standalone, despite getting logon responses from the domain 
controller.

RESOLUTION
==========

Buffers controlling datagrams were being exhausted and not being 
recycled.

Binary Affected
---------------

TINYRFC.EXE
TCPTSR.EXE
TCPDRV.OS2


-------------------------------------------------------
TCP/IP Server Won't Send Datagrams; BDCs Go Out of Sync
-------------------------------------------------------

SYMPTOMS
========

Servers running the TCP/IP protocol would, after a period of time, 
stop sending server announcements, which would in turn cause the 
domain controllers to fall out of sync.

RESOLUTION
==========

Code that was not freeing packets has been changed.

Binary Affected
---------------

NBDRV.OS2
TCPDRV.OS2


----------------------------------------------------------
BCASTADDR Parameter in PROTOCOL.INI Ignored by OS/2 TCP/IP
----------------------------------------------------------

SYMPTOMS
========

Under OS/2, TCP/IP was ignoring the BCASTADDR parameter in the 
PROTOCOL.INI file. 

RESOLUTION
==========

This functionality was added.

Binary Affected
---------------

NBDRV.OS2


-------------------------------------------
All TCP/IP Servers on Net Trap in NBDRV.0S2
-------------------------------------------

SYMPTOMS
========

A particular packet sent on the network as a broadcast was causing 
servers to crash with the following register information:

CSLIM=9850
IP=00E0
BP=0738
SI=0000

RESOLUTION
==========

The software now checks for a null pointer. 

Binary Affected
---------------

NBDRV.OS2


-----------------------------------
Server Crashes and Issues TRAP 0003
-----------------------------------

SYMPTOMS
========

A server crashed with the following output:

TRAP: 0003

AX=0D60 BX=2242 CX=1000 DX=DEAD BP=071E
SI=2242 DI=0000 DS=0D68 ES=0DA0 FLG=2246
CS=0D60 IP=017F SS=1920 SP=071E MSW=001B
CSLIM=1680 SSLIM=07FF DSLIM=FECF ESLIM=36F7
CSACC=9B SSACC=93 DSACC=93 ESACC=F3

RESOLUTION
==========

An invalid instruction has been changed.

Binary Affected
---------------

TCPDRV.OS2


---------------------------------------------------------
Sybase Server Doesn't Respond to TCP/IP "Cancel" Commands
---------------------------------------------------------

SYMPTOMS
========

The Sybase SQL server did not respond to "Cancel" commands issued 
through the TCP/IP SQL server gateway. 

RESOLUTION
==========

Support for the out-of-band data signal was added.

Binary Affected
---------------

SOCKETS.EXE
SOCKETS.OS2


--------------------------------------------------------
TCP/IP MS-DOS Utilities Cannot Connect with IBM 3090 MVS
--------------------------------------------------------

SYMPTOMS
========

Ftp and other TCP/IP MS-DOS DOS utilities cannot connect to IBM 3090 
MVS systems

RESOLUTION
==========

MVS will not reply unless the PUSH bit is set on each packet, so the 
ForcePushBit parameter has been added to the [TCPIP] section of the 
PROTOCOL.INI file. It defaults to 0, but when it is set to 1 it causes 
the PUSH bit to be set on every outgoing packet. 

Binary Affected
---------------

TCPTSR.EXE


-----------------------------------------------------------------
Information Packets Incorrectly Reassembled After Crossing Router
-----------------------------------------------------------------

SYMPTOMS
========

TCP/IP packets that were fragmented as they passed through routers 
were not being correctly reassembled.

RESOLUTION
==========

Changed the code to reassemble fragmented packets correctly.

Binary Affected
---------------

TCPDRV.OS2
TCPTSR.EXE


----------------------------------------------
TCP/IP Returns Wrong Error Code on Failed Call
----------------------------------------------

SYMPTOMS
========

When a server would go down for a client-server application (in this 
case, Schedule+), TCP/IP would cause the client application to hang.

RESOLUTION
==========

The NetBIOS return code was changed so that the application would 
recover gracefully.

Binary Affected
---------------

TINYRFC.EXE


----------------------------------------------
LM Server Trap D's in TCPDRV When Sent LLC XID
----------------------------------------------

SYMPTOMS
========

A server running TCP/IP was crashing with the following output screen:

TRAP 000D
AX=0104     BX=0000     CX=0000     DX=07F8     BP=0770
SI=085C     DI=016C     DS=07C0     ES=07F8     FLG=2206
CS=07B0     IP=0FF9     SS=1918     SP=0764     MSW=001B
CSLIM=98E0  SSLIM=07FF   DSLIM=FECF  ESLIM=5DCB
CSACC=9B    SSACC=93     DSACC=93    ESACC=F3
ERRCD=694C    ERLIM=****    ERACC=**

RESOLUTION
==========

Changed the code so that the packet was not accepted.

Binary Affected
---------------

TCPDRV.OS2


-----------------------------------------------------------------
TCP/IP Server Routes Traffic from Token Ring to Ethernet, Crashes
-----------------------------------------------------------------

SYMPTOMS
========

A server running TCP/IP on token ring was crashing with a Trap D when 
traffic was routed between a multi-ringed token ring network and an 
Ethernet network. The IP register was 1629.

RESOLUTION
==========

Rather than continuing to re-use a buffer, a fix was installed to 
allocate a new buffer to ensure that space for routing information was 
always available.

Binary Affected
---------------

TCPDRV.OS2


--------------------------------------------------------------
Error 53--TCPCONNECTIONS Depleted, Connection Denied to Client
--------------------------------------------------------------

SYMPTOMS
========

A server would run out of TCPCONNECTIONS and issue Error 53 to clients 
that attempted to connect to it.

RESOLUTION
==========

Timeout code was added for the TCP/IP FINWAIT-2 state.

Binary Affected
---------------

TCPDRV.OS2

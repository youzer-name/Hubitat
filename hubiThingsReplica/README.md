<h1>HubiThings Replica</h1>

A [Hubitat application](https://community.hubitat.com/t/release-hubithings-replica/107976) to allow real-time bi-direction updates between Hubitat and SmartThings devices, modes, scenes, weather and push notifications utilizing the SmartThings OAuth Cloud API. Includes the ability to have multiple ST locations with multiple ST hubs replicated to a single Hubitat hub. It is not a requirement to have a ST hub to operate mirror functions to cloud native ST devices.

This solution requires a reasonable degree of understanding of both Hubitat and SmartThings. The original design was to mirror the few devices I have remaining in SmartThings to Hubitat in a real time fashion, but grew into a full project thanks to @Alwas, @bthrock, @hendrec, @swade, and @hendo25.

One primary use is to allow ST [webCoRE](https://community.hubitat.com/t/webcore-documentation-digest/88285) users to continue enjoying that application operating on Hubitat. Please note, this is NOT a replacement for [HubConnect](https://community.hubitat.com/t/release-hubconnect-share-devices-across-multiple-hubs-no-longer-smartthings/12028) and doesn't operate the same. <i>Obvious shout out to both incredible products</i>.

The HubiThings Replica application collects the capabilities of the ST device and stores the information in the HE device data section. Then using 'rules' to define commands and attributes from both the ST device and HE device establishes mirror functions. The HubiThings OAuth application drives real-time communication between ST and HE and issues those events to Replica. There are native Replica devices handlers and they auto-configure 'rules' for you - suggest you use them.
There are two required applications and many and growing native Replica device handlers (not required but advised).

HubiThings Replica (Install first):<br/>
Location: https://raw.githubusercontent.com/bloodtick/Hubitat/main/hubiThingsReplica/hubiThingsReplica.groovy<br/>
Installation: Load into the 'Apps code' area of HE. You do not need to enable OAuth for this application.

HubiThings OAuth (Install second):<br/>
Location: https://raw.githubusercontent.com/bloodtick/Hubitat/main/hubiThingsReplica/hubiThingsOauth.groovy<br/>
Installation: Load into the 'Apps code' area of HE. <b>You MUST ENABLE OAuth for this application</b>.

Replica Device Handlers:<br/>
Location: https://github.com/bloodtick/Hubitat/tree/main/hubiThingsReplica/devices<br/>
Location: https://github.com/TheMegamind/Replica-Drivers<br/>
Location: https://github.com/dds82/replica<br/>
Location: https://github.com/DaveGut/HubithingsReplica<br/>
Installation: Load into the 'Drivers code' area of HE. You can load as many, or as few as needed. The application is looking for any DH that has namespace 'replica'. If you want to design your own, please let me know and we can post locations here for others to use!

Operation:
1. Install from the "Add User App" section "HubiThings Replica".
2. Replica will prompt you to close after install and then reopen.
3. Supply a full credited [SmartThings PAT](https://account.smartthings.com/tokens) which will then allow the OAuth application to be accessed.
4. Follow the prompt and install a HubiThings OAuth (it is a child app).
5. Continue to follow the OAuth prompts and when successful you are able to pick ST devices to mirror.
6. Return back to the Replica app and you should see the device(s) in the 'HubiThings Device List'.
7. Click 'Configure HubiThings Devices' and follow the creation process. (Start easy with a simple ST device and use a Replica DH).
8. If #7 was a Replica DH, the rules and device will auto configure and you are ready, if you pick a Virtual device, you will now need to go to "Configure HubiThings Rules" and match attributes to commands.

:point_right: NOTE: SmartThings is changing their PAT policy to only be valid for 24 hours, as of Replica version 1.5.00 you will need a valid PAT to create and delete the HubiThings OAuth API. There appears to be a bug on creating virtual devices that needs a valid PAT which hopefully is resolved quickly. See SmartThings topic [here](https://community.smartthings.com/t/changes-to-personal-access-tokens-pat/292019).

Update 2023/01/13: Release 1.3.00. Change log [here](https://community.hubitat.com/t/beta-hubithings-replica/107976/152).<br/>
Update 2023/01/17: Release 1.3.00. Added to HPM. For existing installs see [here](https://community.hubitat.com/t/release-hubithings-replica/107976/185).<br/>
Update 2023/01/29: Release 1.3.02. Change log [here](https://community.hubitat.com/t/release-hubithings-replica/107976/233).<br/>
Update 2023/02/10: Release 1.3.03. Change log [here](https://community.hubitat.com/t/release-hubithings-replica/107976/249).<br/>
Update 2023/02/19: Release 1.3.05. Change log [here](https://community.hubitat.com/t/release-hubithings-replica/107976/261).<br/>
Update 2023/02/26: Release 1.3.06. Change log [here](https://community.hubitat.com/t/release-hubithings-replica/107976/266).<br/>
Update 2023/03/14: Release 1.3.07. Change log [here](https://community.hubitat.com/t/release-hubithings-replica/107976/291).<br/>
Update 2023/04/23: Release 1.3.08. Change log [here](https://community.hubitat.com/t/release-hubithings-replica/107976/323).<br/>
Update 2023/06/05: Release 1.3.09. Change log [here](https://community.hubitat.com/t/release-hubithings-replica/107976/334).<br/>
Update 2023/06/17: Release 1.3.10. Change log [here](https://community.hubitat.com/t/release-hubithings-replica/107976/348).<br/>
Update 2023/07/05: Release 1.3.11. Change log [here](https://community.hubitat.com/t/release-hubithings-replica/107976/350).<br/>
Update 2023/08/06: Release 1.3.12. Change log [here](https://community.hubitat.com/t/release-hubithings-replica/107976/377).<br/>
Update 2024/07/28: Release 1.4.00. Change log [here](https://community.hubitat.com/t/release-hubithings-replica/107976/475).<br/>
Update 2024/12/20: Release 1.5.00. Change log [here](https://community.hubitat.com/t/release-hubithings-replica/107976/496).<br/>

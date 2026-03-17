# Base for this example

Cet exemple est généré sur le PLC [Adp_lab_03_Robot_v_3_6](https://github.com/hei-dls-adp/adp_lab_03_2026)



---

## Base de travail pour les exemples: 

**From CtrlX Bosch Rexroth**
[Calling PLC Methods via OPC UA on ctrlX CORE](https://community.boschrexroth.com/ctrlx-automation-how-tos-qmglrz33/post/calling-plc-methods-via-opc-ua-on-ctrlx-core-kGkY2ovWF0BwqV1)

[How-to run an OPC UA Information Model on ctrlX OPC UA Server](https://community.boschrexroth.com/ctrlx-automation-how-tos-qmglrz33/post/how-to-run-an-opc-ua-information-model-on-ctrlx-opc-ua-server-NlKrL5vLkhj3Saq)

**From FlowFuse**
[OPC UA Tutorial: Connect and Exchange Data with Industrial Equipment](https://flowfuse.com/blog/2025/07/reading-and-writing-plc-data-using-opc-ua/)

[HEVS_Version_Of_UA_Tutorial](HEVS_Version_Of_UA_Tutorial.md)


### How do I find an OPC UA Node ID?
Use the OPC UA Browser node in Node-RED to explore the server’s address space. Start with ns=0;i=85 (root Objects folder) and navigate through the hierarchy. Each tag will show its Node ID in the format ns=[namespace];i=[identifier] or ns=[namespace];s=[string identifier].

Or use [OPC UA Clients – Downloads from UAExpert](https://www.unified-automation.com/downloads/opc-ua-clients/uaexpert.html) it is to be considered as the reference tool to test OPC-UA servers.


**From UAExpert**
[Creating Information Models with OPC UA](https://www.unified-automation.com/downloads/webinars/creating-information-models.html)
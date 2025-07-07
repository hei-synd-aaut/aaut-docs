# Tu peux faire un nouveau modules basé sur ce truc:

https://www.isa.org/intech-home/2018/november-december/features/cybersecure-isa-88-recipes-and-control-with-iec-61

[Cybersecure ISA-88 recipes and control with IEC 61131-3](https://www.isa.org/intech-home/2018/november-december/features/cybersecure-isa-88-recipes-and-control-with-iec-61)




Cybersecure ISA-88 recipes and control with IEC 61131-3
By Gary L. Pratt, PE, Timothy L. Triplett, PE
Web Exclusive
Summary

By Gary L. Pratt, PE , and Timothy L. Triplett, PE

Due to hardware and software limitations, batch control systems have evolved as two distinct parts: equipment control in the distributed control system (DCS) or programmable logic controller (PLC), and recipe operations in a separate PC server. Historically, controllers have simply not had the storage and computational power required to handle the entire job. Nor were traditional industrial control system (ICS) programming languages up to the task. Fortunately, 21st century industrial controllers now have sufficient capacity, and 21st century industrial programming languages, such as IEC 61131-3, have sufficient capabilities to consolidate the entire operation in one place. As a bonus, this consolidation is occurring just in time to address the 21st century cybersecurity vulnerabilities inherent in the traditional split system.

Creating an ISA-88 batch system in IEC 61131-3 languages begins in the same way as any object-oriented design. First, build your equipment "Types," such as sensors, pumps, and augers (this effort is greatly simplified if you have a base class of common functionality from which to derive the equipment classes). Then, assemble instances of these "Types" into a control and equipment (C&E) view with input devices on the left, output devices on the right, and control in the center.

The center control block typically contains PIDs for a continuous process and sequential logic for a discrete process. However, in ISA-88, the control block is made up of "equipment phases" that carry out various functions on the equipment. Every equipment phase has matching recipe phases, which will be discussed later.

To put this into practical terms, say you were putting together an ISA-88 module for a mixing tank. The C&E view would have the typical sensors on the left, and pumps and valves on the right, but the control in the center is now made up of "equipment phases" as shown in figure 1. Each of these equipment phases is made up of a standard ISA-88 sequential function chart (SFC) as show in figure 2. The steps and transitions in the equipment phase SFC are the same for all phases. The difference comes in the actions associated with those steps, which may be expressed in any of the IEC 61131-3 languages.


Figure 1. Control and equipment view and details of the control block


Figure 2. Standard ISA-88 phase state machine implemented in IEC 61131-3 sequential function chart
Customizing the standard ISA-88 equipment phase is simplified by the concept of "Inheritance," which has long been available in higher-level languages (like C++ and Java) and is now becoming available to the ICS world. The standard ISA-88 equipment phase is designed into a standard base class that has default entry, exit, and active actions for each step of the state machine. Specific "equipment phases" are then derived from this base class, and the default base class actions are overridden with unique actions required by that specific equipment phase.

Figure 3 shows an example where the "MixTank MixPhase" phase is derived from the "phase" base class. The default behavior of the standard ISA-88 SFC is adequate except for RunningEntry and RunningActive where the base class functionality is overridden by methods in the derived class.

 


Figure 3. Equipment phases are derived from a base class with functionality added by overriding the base class methods.

The other half of the ISA-88 equation is the "recipe" processing. The recipe portion is traditionally implemented on an external PC for the reasons described in the first paragraph. Fortunately, with the power of IEC 61131-3 and modern controller hardware, this function can now be implemented directly in the controller with the same development environment and language as the control code. It is no longer necessary to learn two totally different languages in two totally different design environments. The IEC 61131-3 concepts of inheritance, instantiation, pointers, dynamic memory, and sequential function charts greatly facilitate ISA-88 batch programming in this environment.
In ISA-88, a recipe is a set of nested state machines beginning with the recipe, which may contain one or more procedures, which may contain one or more operations that will contain one or more recipe phases. The IEC 61131-3 SFC is an ideal tool for implementing these state machines. Furthermore, the recipes can have parameterized inputs to allow a great deal of flexibility in the recipe design. The left side of figure 4 shows a simple example of a recipe and one of its procedures. Notice "TargetViscosity" is a parameterized input.

 


Figure 4. A simple recipe implemented in SFC driving a simple equipment phase

Recipes also accept pointers to the equipment on which they are to be executed. In a simple system where the operator chooses the equipment, these pointers can be specified from the human-machine interface (HMI). In more complex systems, the recipe can request certain types of equipment as they become required in the process, and dynamic resource allocation logic on the controller can provide pointers to instances of those equipment types as they become available.
These equipment instance pointers are then passed down through the recipe chain to the recipe phases, which then use them to access their corresponding equipment phases on the intended equipment. Pointers provide a very flexible and efficient means for making this connection. Figure 4 shows the syntax that is used for the recipe to connect to the "Mix Equipment" phase.

Because the equipment is all fixed tangible assets, the equipment can be instantiated as normal. However, the number and type of recipes is in constant flux, so it would be very inefficient to instantiate these in the traditional way. Fortunately, IEC 61131-3 implementations have the capability to dynamically instantiate objects. Figure 5 illustrates how this works. As described above, parameterized recipe "Types" are defined by the process engineer and stored in the controller. The names of these recipes are then provided to the HMI for the operator to choose from. Once the operator chooses a recipe and specifies its parameters, the recipe manager then creates and executes dynamic instances of that recipe. When the recipe operation is complete that memory is freed to accommodate the next recipe.

 


Figure 5. Dynamic recipe instances and equipment pointers

Implementing an entire ISA-88 batch system within the controller has many advantages, including simplification (only one development environment and one language), portability (by implementing the entire system in an industry-standard language), a greatly simplified HMI (used only to select the recipes), and improved uptime (once a recipe is selected, the controller processes the batches with complete and secure autonomy).
But perhaps the greatest advantage occurs when the ISA-88 batch system is implemented on cyber-hardened hardware that has layered and embedded cybersecurity down to the chip level. (figure 6). With the entire ISA-88 process implemented on cybersecure hardware, the days of risking critical operations and intellectual property to proprietary control hardware and consumer-grade PCs can fade to a distant, unpleasant memory.


Figure 6. Controllers with intrinsic cybersecurity bring the advantages of a standardized batch system while keeping operations details and intellectual property safe.
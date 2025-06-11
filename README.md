# cs6250---spanning-tree-solved
**TO GET THIS SOLUTION VISIT:** [cs6250 – Spanning Tree Solved](https://mantutor.com/product/cs6250-spanning-tree-solved-2/)


---

**For Custom/Order Solutions:** **Email:** mantutorcodes@gmail.com  

*We deliver quick, professional, and affordable assignment help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;95042&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;5&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (5 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;cs6250 - Spanning Tree Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (5 votes)    </div>
    </div>
CS 6250

Spanning Tree

Table of Contents

PROJECT GOAL 2

Part 1: Setup 2

Part 2: Files Layout 2

Part 3: TODOs 3

Part 4: Testing and Debugging 5

Part 5: Assumptions and Clarifications 5

What to Turn In 6

What you can and cannot share 7

Rubric 8

PROJECT GOAL

In the lectures, you learned about Spanning Trees which can be used to prevent forwarding loops on a layer 2 network (Modules-&gt;Lesson 1-&gt; Looping Problem in Bridges and the Spanning Tree Algorithm). In this project, you will develop a simplified, distributed version of the Spanning Tree Protocol that can be run on an arbitrary layer 2 network topology. We will simulate the communications between switches with Messages. The goal is to converge on a single solution and output the final spanning tree to a file.

Part 1: Setup

Download the project files from Canvas in the course VM. Alternatively, you can do this project on your host system if it has Python 3.10.x. The project does not have any dependencies outside of Python. You must be sure that your submission runs properly in Gradescope. Gradescope is the environment where your project will be graded. Gradescope and the VM are the only valid environments for this course.

Part 2: Files Layout

There are many files in the SpanningTree directory, but you should only modify Switch.py, which represents a layer 2 switch. You will implement the functionality of the Spanning Tree Protocol to generate a Spanning Tree for each Switch.

• Topology.py – Represents a network topology of layer 2 switches. This class reads in the specified topology and arranges it into a data structure that your Switch can access.

• StpSwitch.py – A base class of the derived class you will code in Switch.py. The base class StpSwitch.py abstracts certain implementation details to simplify your tasks.

• Message.py – This class represents a message format you will use to communicate between switches, similar to the course lectures. Specifically, you will create and send messages in Switch.py by declaring a message as:

msg = Message(claimedRoot, distanceToRoot, originID, destinationID, pathThrough)

• run.py – A simple “main” file that loads a topology file (see XXXTopo.py below), uses that data to create a Topology object containing Switches, and runs the simulation.

• XXXTopo.py, etc. – These are topology files that you will pass as input to the run.py file.

Part 3: TODOs

This is an outline of the code you must implement in Switch.py with suggestions for implementation. Your implementation must adhere to the “spirit of the project”: it should be a distributed solution. We also provide a walkthrough video that covers this part. Past students have found that to be very helpful. Please keep an eye out for that link on Ed Discussion.

A. Decide on the data structure(s) that you will use to keep track of the spanning tree.

1. The collection of active links across all switches is the resulting spanning tree.

3. This is a distributed algorithm. The switch can only communicate with its neighbors.

It does not have an overall view of the spanning tree, or the topology as a whole.

4. An example data structure should include, at a minimum:

a. a variable to store the switch ID that this switch sees as the root,

b. a variable to store the distance to the switch’s root,

c. a list or other datatype that stores the “active links” (only the links to neighbors that are in the spanning tree).

d. a variable to keep track of which neighbor it goes through to get to the root (a switch should only go through one neighbor, if any, to get to the root).

6. It is important to create a data structure in the correct place in Python (as in most object-oriented programming languages). If you create it inside a method, every time the method is called it will be recreated. You should create a class member in the class constructor so that the data stored in the object exists for the life of the instance. For example self.mylist = [ ] in the constructor should create an empty list data structure and act as instance variable. But if mylist were instantiated in self.process_messages, it will be created every time that method is called.

B. Implement processing a message from an immediate neighbor.

1. For each message a switch receives, the switch will need to:

a. Determine whether an update to the switch’s root information is necessary and update accordingly.

I. The switch should update the root stored in its data structure if it receives a message with a lower claimedRoot.

II. The switch should update the distance stored in its data structure if

a) the switch updates the root, or b) there is a shorter path to the same root.

b. Determine whether an update to the switch’s active links data structure is necessary and update accordingly. The switch should update the activeLinks if:

I. The switch finds a new path to the root (through a different neighbor). In this case, the switch should add the new link to activeLinks and (potentially) remove the old link from activeLinks

II. The switch receives a message with pathThrough = TRUE but does not have that originID in its activeLinks list. In this case, the switch should add originID to its activeLinks list.

c. Determine whether the switch should send new messages to its neighbors and send those messages.

I. This is an important design decision. There are many correct algorithms that send messages at different times. The algorithm has converged to the Spanning Tree when no more messages are sent.

II. The message FIFO queue is maintained in Topology.py. The switch implementation does not interact with the FIFO queue directly, but uses the send_message function, and receives messages as arguments in the process_message function.

III. When sending messages, pathThrough should only be TRUE if the destinationID switch is the neighbor that the originID switch goes through to get to the claimedRoot. Otherwise, pathThrough should be FALSE.

C. Write a logging function.

1. The switch should only output the links that are in the spanning tree.

2. Follow the below format (# – #). Unsorted or non-standard formatting will result in penalties. Examples of correct logs with the correct format have been provided to you.

3. Sorted: Not sorted:

1 – 2, 1 – 3 1 – 3, 1 – 2

2 – 1, 2 – 4 2 – 4, 2 – 1

3 – 1 3 – 1

4 – 2 4 – 2

Part 4: Testing and Debugging

To run your code on a specific topology (SimpleLoopTopo.py in this case) and output the results to a text file (out.txt in this case), execute the following command:

python run.py SimpleLoopTopo

“SimpleLoopTopo” is not a typo in the example command – don’t include the .py extension.

We have included several topologies with correct solutions for you to test your code against. You can (and are encouraged to) create more topologies and test suites with output files and share them on Ed Discussion. There will be a designated post where students can share these files.

You will only be submitting Switch.py – your implementation must be confined to modifications of that file. We recommend testing your submission against a clean copy of the rest of the project files prior to submission.

You should add print statements to facilitate debugging during your development process, but they should be removed or commented out prior to submission.

Part 5: Assumptions and Clarifications

A. All switch IDs are positive integers, and distinct.

1. These integers do not have to be consecutive.

2. They will not always start at 1.

3. There is no maximum value beyond language (Python) limitations (which your code does not need to check for).

B. Tie breakers: If there are multiple paths of equal distance to the same root, the switch should choose the path through the neighbor with the lowest switch ID.

1. Example: switch 5 has two paths to root switch 1, through switch 3 and switch 2. Each path is 2 hops in length. Switch 5 should select switch 2 as the path to the root and disable forwarding on the link to switch 3.

C. There is a single distinct solution spanning tree for each topology. This is guaranteed by the first two assumptions.

D. All switches in the network will be connected to at least one other switch, and all switches are able to reach every other switch. It will always be possible to form a tree that spans the entire topology.

E. There will be only 1 link between each pair of directly connected switches. You do not need to consider how STP would behave with redundant links.

F. The topology given at the start will be the final topology. The topology will not change while your code is running (i.e., adding a switch, severing a connection, etc.)

H. The solution implemented in Switch.py should terminate without intervention. When there are no more messages in the queue to process, the simulation will log output and self-terminate.

I. Your solution should not require any outside Python modules. Please do not import any other modules.

What to Turn In

Before submission:

a. Make sure your logging format is correct. Invalid format will result in penalties.

b. Remove any print statements from your code before turning it in. Print statements can have drastic effects on runtime. Your submission must take less than 10 seconds per topology. If print statements in your code adversely affect the grading process, your work will not receive full credit.

c. Make sure your Switch.py works in Gradescope. Gradescope will give you immediate feedback, along with your grade, so we will not accept re-grade requests related to incorrect submissions.

e. Helper functions: Helper functions are fine, as long as the names don’t conflict with anything already in the file. If it works in Gradescope, it is fine.

After submission:

g. Your grade in Gradescope will be your grade for this project, with some caveats:

b. Any “hard-coded” solutions that violate the “spirit of the project” will be regraded manually.

What you can and cannot share

Rubric

10

pts Correct

Submission For turning in the correct file with the correct name. You receive 10 FREE points for reading the instructions.

45

pts Provided

Topologies For correct Spanning Tree results (log files) on the provided topologies.

45

pts Unannounced

Topologies For correct Spanning Tree results (log files) on three topologies that you will not have access to. These cases are used to prevent students from hardcoding a solution.

Grading Note: Partial credit is not available for individual topology logs. The output must be fully correct to receive credit – a single link discrepancy will result in a zero for that topology. Additionally, we will be using many topologies to test your project, including but not limited to the topologies we provide, and checking for corner cases not exhibited in the sample topologies provided.

The goal of this project is to implement a simplified version of a network protocol using a distributed algorithm.

The skeleton code we provide you runs a simulation of the larger network topology, and for the sake of simplicity, the StpSwitch class defines a link to the overall topology. This means it is possible using the provided code for one Switch to access another’s internal state. This goes against the “spirit of the project”. Additional detail is available in the comments of the skeleton code.

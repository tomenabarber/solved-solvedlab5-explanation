Download Link: https://assignmentchef.com/product/solved-solvedlab5-explanation
<br>
This lab is about simulation of different memory allocation techniques welearned in week4 such as (first fit, next fit and other techniques).

Select and simulate one of these techniquesfor lab4 and select another technique for lab5.

Assumptions:

Memory is 256K.

Each unit is 2K. Therefore, there are 128units that can be allocated to different processes.

Aprocess may request between 3 and 10 units of memory

Number of requests: 10,000

Based on the above assumptions, threeconstants are defined in the code as follows:

#define NUM_REQUESTS 10000

#define MIN_NUM_UNITS 3

#define MAX_NUM_UNITS 10

A class is defined called Node which hastwo member variables called process_id and num_units.

Also a list of nodes needs to be defined.

At start all the units are available. Wecan use -1 as the process_id to represent availability (hole). The following diagram shows the list at thestart where the 128 units is available for allocation. Note however, a processcan only ask for up to 10 units of allocation.

-1

128

The program uses a random generatorfunction to randomly select between allocation and deallocations. The deallocations can happen if there is atleast one process that memory is allocated for it.

You can keep track of the list of processesthat the memory is currently being allocated to them. Then during the deallocation, you mayrandomly select one process from this list and deallocate memory for thatprocess.

Each allocation or deallocation isconsidered as one request. You must alsokeep track of number of requests since we want to have 10,000 requests in thissimulation.

Each process may request 3 to 10 units ofmemory. Therefore, number of unit requested by each process is a random numberin the range 3 to 10. You may use avariable called nextProcessId and at the end of each allocation request, youmay increment that variable for the next process ID request.

You may use a for loop to check the list tosee if there is a hole big enough for the given request as follows:

for (list memory_list.begin(); cur != memory_list.end(); ++cur) {

As you check each node, if a node has aprocess id of -1 and the size of it is equal or greater than the requestednumber of units then allocation is possible.

You need to modify the list by inserting anode with the given process ID and given number of units requested.

Example:

If process 0 requests 5 units, then theabove list becomes:

0

5

-1

123

Next time we do an allocation, we musttraverse the list more to find a free location.

As we do deallocations, we will get morethan one hole. If the size of a hole is1 or2 units, then we have fragments.

You can also define two constants:

#define HOLE_PROCESS_ID -1

#define MAX_FRAGMENT_NUM_UNITS 2

There are three performance parameters that your simulation shouldcalculate for the chosen two techniques: averagenumber of external fragments, averageallocation time in terms of the average number of nodes traversed inallocation, and thepercentage of times an allocation request is denied.

Each time allocation is successful, thenumber of traversals is returned. You should have a variable to keep track ofthe total number of traversals. Also you should have a variable to keep trackof the number of allocation successes.These two values can be used to calculate the average of number of nodestraversed. In addition, when there is a successful allocation, your code shouldfind the number of fragments. A variable should keep track of total fragments.

Find attached solution
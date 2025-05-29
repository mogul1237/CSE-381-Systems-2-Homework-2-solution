# CSE-381-Systems-2-Homework-2-solution

Download Here: [CSE-381: Systems 2 Homework #2 solution](https://jarviscodinghub.com/assignment/cse-381-systems-2-homework-2-solution/)

For Custom/Original Work email jarviscodinghub@gmail.com/whatsapp +1(541)423-7793

Develop program to print group membership
Objective
The objective of this program is to print login-IDs of the users belonging to a given set of gids
specified as command-line arguments. The necessary data is read from 2 given text files.
Background
In Linux, users are internally represented using a unique number called user ID of uid.
Moreover, a set of users can be logically organized into a group. Such groups are represented by
a group ID or gid. Typically, these numbers are seldom used and instead a name is associated
with these numbers and the names are often used. This program will serve as an excellent tool to
quickly identify membership in a given group.
Data file formats
Prior to solving any problem is important to study the supplied data. So ensure you view the data
files (yes, of course you can do this in NetBeans). The supplied data files used are nearly in the
same format as they are in a real Linux OS as described below. Needless to add, you will need to
copy these files to your NetBeans project in order to read/use them.
• User data (passwd): The supplied passwd file contains user information in the
following colon (:) delimited format:
loginID:passkey:uid:…
For example the following line from passwd “raodm:xyz:1000:…” contains the
login ID raodm as the first entry, xyz is some passkey (not used) followed by the uid
(int). Rest of the information in the line is not used.
• Group information (groups): The supplied groups file contains group information
in the following colon (:) delimited format:
groupID:passkey:gid:members…
For example the following line from groups “staff:x123:3:1002,1000”
contains the group ID staff as the first entry, x123 is some passkey (not used)
followed by the gid (int), followed by a comma separated list of uids. This results in
group corresponding to output “3 = staff: lewisjp3(1002)
raodm(1000)”, where the uid for each member is shown in parentheses.
DUE DATE: Tue, September 18 2018 Before 11:59 PM (EST)
Page 3 of 3
Sample outputs
One you have completed your program, you can test its operation using the command shows
below and compare your output to the output shown below. Note that group IDs are
Base case #1:
$ ./raodm_hw2 0
0 = root: root(0)
Base case #2:
$ ./raodm_hw2 1
1 = bin:
Test case #3 [Must pass to earn full points]:
$ ./raodm_hw2 100
100 = Group not found.
Test case #4 [Must pass to earn full points]:
$ ./raodm_hw2 0 1 2 6 100 6 2
0 = root: root(0)
1 = bin:
2 = faculty: raodm(1000) campbest(1001) kiperjd(1003) raychov(1004)
bachmaer(2000) inclezd(1500) davisk4(2001) femianjc(2002) crossv(2010)
castroa(2011) ahmede(2012)
6 = theory: davisk4(2001) inclezd(1500) raychov(1004) femianjc(2002)
100 = Group not found.
6 = theory: davisk4(2001) inclezd(1500) raychov(1004) femianjc(2002)
2 = faculty: raodm(1000) campbest(1001) kiperjd(1003) raychov(1004)
bachmaer(2000) inclezd(1500) davisk4(2001) femianjc(2002) crossv(2010)
castroa(2011) ahmede(2012)
Notes/Tips:
• Use std::istringstream to process each line. See example in slides on processing
Comma Separated Values (in this example, instead of comma you are using colons)
• Use a unordered_map to store uid⇔loginID information to ease look-up from
processing group membership.
• It would be easier to compute and store the line of output to print for each gid in another
unordered_map.
Submit to Canvas
This homework assignment must be turned-in electronically via Canvas via the CODE Plugin.
Ensure your program compiles without any warnings or style violations and operates correctly, at
least for the base case. Once you have tested your implementation, upload just one C++ source
file via the CODE plugin.

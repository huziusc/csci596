# csci596
# This project is based on codes from a paper under submission. For this reason, I won't present the code but only this README file for some description.
#######################################
# Project Description
# A ride-sharing operation with 500 drivers and 1000 passenger requests in DTLA region.
# Passenger requests come in as a Poisson process while drivers are heading towards their own destination.
# Each vehicle has a capacity of 4.
# Each driver and passenger has a time limit of how much time they are willing to stay in the vehicle.
# After assigning and routing each passenger with a simple VRP heuristic, we need to calculate and compare 3 different cost-sharing methods (compute the shared cost each passenger needs to pay in the end, this cost is first computed at the submission of the request and will continue to change till the end of the operation.)
# Each passenger has an upper-bound in paying their shared cost. This means that if the initial quotes provided to the passengers at the submission of their requests are higher than expected, then they will not join the operation.
# In order to compare the different method, we randomly generate 100 instances and compute the average results, in each instance, the demand and locations are randomly generated as well.
#######################################
# Reason to parallel
# Currently, for the scenario of 500 drivers and 1000 passenger requests and 3 cost-sharing methods, each instance needs to run approximately 5 minutes. 100 instances would be 500 minutes (13.9 hrs). And I have multiple scenarios to run.
# Paralleling the computation would give a boost in time efficiency.
# So I decided to parallel the computation of multiple instances into multiple cpu cores.
#######################################
# Results
# On my AMD Ryzen 9 3900X 12-core CPU, using 10 cores allows me to process 100 instances for a scenario in 75 minutes which is a great boost in time compared to the 500 minutes.

# protocol_change_for_loadbalancing
# Objective<br>
Remove additional hardware or software to remove traffic load balance among instances<br>
Protocol independent methodology<br>
Enable customize load balancing<br>
Eliminate high capacity for load balance device.<br>


# Methodology<br>
Initial control node is to be discovered by DNS<br> 
Initial session will be establish to control node.<br>
Control node response with next node ip ( no change in domain name)<br>
End client will initiate session toward to new ip without looking at DNS ip.<br>
Service will continue with new instance ip.<br> 
Traffic will migrate to Control node to worker nodes.<br>

# Example1- HTTP protocol load balance implementation <br>
User enter  example.com in URI.<br>
DNS request send to resolver to get ip (control node ip)<br>
Browser send GET request to resolved ip.<br>
Server send Response with Header field “X-New-IP : x.x.x.x” <br>
If browser sees response header<br>
&nbsp;Browser send next requests to  X-New-IP ip address without looking at DNS.<br>

Note: This is just example and open for discussion.

#Example2-DNS resolver load balance.<br>
Introduce New Resource Record Type “RESOLVE”<br>
DNS client send “RESOLVE” request to initial resolver ip.<br>
DNS resolver send New Resolver ip as response.<br>
DNS client will set new ip as its resolver.<br>
DNS traffic will diverted to new worker nodes servers.<br>
Upon Revolver failure Client send “RESOLVE” request to its original resolver.<br>

#Conclusion
Load balancing could be customized without special hardware.<br>
Load balancers could be eliminate by Implementing Similar methodology for any protocol.<br> 


# This is open for modification.





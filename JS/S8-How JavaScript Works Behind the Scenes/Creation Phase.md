
let's actually try to simulate the creation phase.

![[Pasted image 20250621041210.png]]

technically none of these values actually ==become known during the creation phase==, but only in the ==execution phase==.

How will the engine keep track of the order in which functions we're called? and how will it know where it currently is in the execution?

that's where [[The Call Stack]] finally comes in.
# How retention policies affect Amazon Chime users<a name="retention-policy-users"></a>

The retention policies that Enterprise account administrators set affect Amazon Chime users differently, depending on whether the users are part of the same Enterprise account, a different Enterprise account, a Team account, or whether the users are not members of any account\.

**Enterprise member chat conversations**  
The following table shows how retention policies affect chat conversations for Enterprise account members\.


| If the chat conversation includes\.\.\. | The retention policy is\.\.\. | 
| --- | --- | 
|  Only other members of the user’s Enterprise account   |  Set by the user’s administrator  | 
|  Anyone outside of the user’s Enterprise account  |  Automatically set to 90 days  | 

**Enterprise member chat rooms**  
The following table shows how retention policies affect chat rooms for Enterprise account members\.


| If the chat room is created by\.\.\. | The retention policy is\.\.\. | 
| --- | --- | 
|  A member of the user’s Enterprise account   |  Set by the user’s administrator  | 
|  Another Enterprise account member  |  Set by the other account’s administrator  | 
|  A non\-Enterprise account member  |  Not applicable  | 

**Team member chat conversations**  
The following table shows how retention policies affect chat conversations for Team account members\.


| If the chat conversation includes\.\.\. | The retention policy is\.\.\. | 
| --- | --- | 
|  Only users who are not members of an Enterprise account   |  Not applicable  | 
|  At least one member of an Enterprise account  |  Automatically set to 90 days  | 

**Team member chat rooms**  
The following table shows how retention policies affect chat rooms for Team account members\.


| If the chat room is created by \.\.\. | The retention policy is\.\.\. | 
| --- | --- | 
|  A Team account user  |  Not applicable  | 
|  Anyone who is not an Enterprise account member  |  Not applicable  | 
|  A member of an Enterprise account  |  Set by the Enterprise account’s administrator  | 

Amazon Chime users who are not members of an Enterprise or Team account are only subject to chat room retention policies in chat rooms that are created by a member of an Enterprise account\.

**Chat conversations with recipients who do not belong to an Enterprise or Team account**  
The following table shows how retention policies affect chat conversations for users who are not members of an Amazon Chime Enterprise or Team account\.


| If the chat conversation includes\.\.\. | The retention policy is\.\.\. | 
| --- | --- | 
|  Only users who are not members of an Enterprise account   |  Not applicable  | 
|  At least one member of an Enterprise account  |  Automatically set to 90 days  | 

**Chat rooms created by users who do not belong to an Enterprise or Team account**  
The following table shows how retention policies affect chat rooms for users who are not members of an Amazon Chime Enterprise or Team account\.


| If the chat room is created by \.\.\. | The retention policy is\.\.\. | 
| --- | --- | 
|  A user who is not a member of an Enterprise or Team account  |  Not applicable  | 
|  A Team account user  |  Not applicable  | 
|  A member of an Enterprise account  |  Set by the Enterprise account’s administrator  | 
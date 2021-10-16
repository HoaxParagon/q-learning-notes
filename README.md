# q-learning-notes
just my simple notes on reinforcement learning. I don't do much with RNNs and textual information but I plan to do lots with Q and autoML. Someone else might find these notes handy as well. Don't count on excellence though.


#### NOTES  
q-learning is a type of reinforcement learning. An agent acts inside of an environment to achieve a reward.  
If the agent does well, it gets a cookie, otherwise, a slap in the face of variable strength according to how badly it did.  

ENVIRONMENT is where the agent explores. Example includes video game world.  
AGENT is the actor which acts on or explores the environment. Example includes video game character.  
STATE is just the status of the agent, a Mario character jumping for instance, or currently in the air, location.  
REWARD is a value with some magnitude based on quality of preceeding action. The skater bot gains a higher score in THPS2 than it did   
    previously, the chess bot won in less moves or took more higher point value pieces sooner.  
Reward is the most important part of the model. The agent is attempting to max out the reward by acting on the environment.  
Reward is a measure of how well the model has done by acting on its environment.  


#### Q-table example
| a1 | a2 | a3 |  
|----|----|----|
| 0  | 5  | 10 |
| 5  | 10 | 0  |

The table above shows each of three actions and the time step. It's a matrix made of states and actions. We zero init this matrix because there are no known states with any previously taken action; we start fresh.  

Each index is updated according to some equation like this one: Q[state,action] = Q[state,action] + learning_rate * (reward + GAMMA * np.max(Q[new_state, :]) - Q[state,action])  
where the value at state and action are updated to the current value + our learning rate * the quantity of our new state's actions - the current value at (state, action).  

During each step some values are calculated such as reward, epsilon or gamma. The next state is also prepared by and received from the step() method.  

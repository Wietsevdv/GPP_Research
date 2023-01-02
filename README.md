# GPP_Research

I will be researching Goal-Oriented-Action-Planning or GOAP for short.

GOAP is a decision making code structure. It revolves around the AI having a goal, and choosing by itself which actions it will take to reach this goal.
Each action has atleast 1 precondition and 1 effect. The AI uses these preconditions and effects to decide what action to take to accomplish its goal.

Example:

-Agent needs to move from room A to room B. The precondition for this action would be that there needs to be a way to get to room B(eg: door not locked).

-Assuming the path is blocked, it cannot go to room B yet. So the agent needs to find an action that has the effect to clear the path(eg: unlock door).

-Following the door example, the unlockDoorAction will have a precondition "HaveKey". The agent needs an action that has the effect "HaveKey = true;".


It boils down to the AI having a goal it wants to make true and choosing performable actions who's effects result in the AI achieving its goal.

This will definitly use a stack. As every action you finish, will make you want to return to the previous action you were trying to perform but needed to first meet its precondition(s).

Start by creating a world where you manually open the door to check these mechanics work. After that make the ai take over with goap

important note: GOAP needs a finite state machine to work. It removes the state transition logic, and makes the FSM much simpler.

GOAP in code will be a "planner" that is giving a goal by the AI. The planner uses pathfinding on nodes that hold worldInfo with actions being the connections that change the worldInfo. The path the planner creates is the sequence of actions the AI can take to realize it's goal. Each action in this sequence changes worldinfo to the point the goal is met.

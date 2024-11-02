## Solana Program Architecture RPG Game

Program Architecture is what separates the hobbyist from the professional. 
Crafting performant programs has more to do with system design than it does with the code. And you, as the designer, need to think about:

1. What your code needs to do
2. What possible implementations there are
3. What are the tradeoffs between different implementations

These questions are even more important when developing for a blockchain. 
Not only are resources more limited than in a typical computing environment, you're also dealing with people's assets.

### Summary
- If your data accounts are too large for the Stack, wrap them in Box to allocate them to the Heap
- Use Zero-Copy to deal with accounts that are too large for Box (< 10MB)
- The size and the order of fields in an account matter; put the variable length fields at the end
- Solana can process in parallel, but you can still run into bottlenecks; be mindful of "shared" accounts that all users interacting with the program have to write to

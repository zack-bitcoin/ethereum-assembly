Ethereum-assembly
========

Assembler for the EVM (ethereum virtual machine). It takes code like:



	\this is a comment
	\ "5 0 0 log1" logs a "5"
	3 3 mul \another comment
	foo jump
	27 0 0 log1 \this code wont be run. we jumped over it.
	jumpdest foo 
	420 0 0 log1 \this code runs 9 times (from 3 and 3 we multiplied above)
	1 swap1 sub    \run 9 times
	dup iszero iszero foo jumpi \this jumps us back to foo
	06 0 0 log1
	


And it returns EVM byte code like: 6003600302600f56601b60006000a15b6101a560006000a160019003801515600f57600660006000a1
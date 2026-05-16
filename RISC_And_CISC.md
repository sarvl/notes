#computer_architecture #isa

Reduced Instruction Set Computer and Complex Instruction Set Computer was major [[Instruction_Set_Architecture|ISA]] design discussion concerning how much stuff should be done by the [[Processor|Processor]] and how much by the [[Compilation|Compiler]]. Due to lack of rigid definition, the term is of little use in practice. Paper *Instruction Sets and Beyond: Computers, Complexity, and Controversy* offers great overview of the topic, albeit a bit dated.
For discussion regarding performance effects see [[Instruction_Set_Architecture#Performance Effects|Performance Effects]].

The concept has been introduced in organized way with *The Case for the Reduced Instruction Set Computer*, but the idea of simplifying instruction set has been already tested by then by few projects like [[IBM_801|IBM 801]]. The primary concerns of that era are not as relevant now, chip space is essentially free and the primary constrain is power consumption.
The authors make very interesting point about how little of ISA is actually commonly used and inclusion of most of instructions does not change the behavior significantly, though they do make a mistake of looking at execution count rather than total execution time, nevertheless their point stands. Addition of more complex instruction does not even necessarily improve the performance in that specific case, it happens that such instructions are forgotten or particularly not convenient to optimize and are thus slow - like with [[x86]] `LOOP` or [[VAX]] `INDEX`. This is true in  general, complex ISAs are harder to get right.

Some early results can be found in [[RISC-I|RISC I]].

Many of the points, especially the instruction count and lack of formal definition, have been criticized in the  *Comments on "The Case for the Reduced Instruction Set Computer", by Patterson and Ditzel*. Regarding compiler writing, authors also indirectly point out that even the definition of instruction itself is not clear, one may define `orw R0, R1` as  different instruction than `orb R0, R1`, when the only difference is size of operands.

The paper *Instruction Sets and Beyond: Computers, Complexity, and Controversy* summarizes many research points and provides working RISC definition
- Single-Cycle operation
- [[Load_Store_ISA|Load Store]]
- [[Control#Hardwired|Hardwired Control]]
- Relatively few instructions
- Fixed instruction format
- More compile time effort

Especially early during research, RISC projects often included different features that were not directly tied up to ISA but rather were a result of less die space used. Despite the criticism, it was actually fair comparison because the entire point of RISC was to free the die resources for features like [[Register_File#Rolling|Rolling Register File]] or [[Cache|Caches]].  Nonetheless, now chip area is usually not a constraint.

More recent research suggests that ISA is not significantly relevant for power efficiency. However claims about efficiency of [[x86]] as exemplary of CISC problems are inaccurate, any long lasting ISA by this point must suffer from growth over the years, unless it was specifically designed for it.

Fundamentally, the problem is focusing on a paradigm to design an ISA rather than carefully considering each design decision. It may be the case that the final design will be typical RISC but it may also be that it differs in crucial way from it.
One important point to note is notion that modern processors are all RISC underneath is preposterous, the split of complex instructions into simple ones is how always things have been done.

## Papers
-  *The Case for the Reduced Instruction Set Computer* by David Patterson, and David Ditzel
-  *Comments on "The Case for the Reduced Instruction Set Computer", by Patterson and Ditzel* by Douglas Clark, and William Strecker
-  *RISC Assessment: a High Level Language Experiment* by David Patterson, and Richard Piepho
-  *Instruction Sets and Beyond: Computers, Complexity, and Controversy* by Robert Colwell, Charles Hitchcock, Douglas Jensen, Brinkley Sprunt, and Charles Kollar
- *Power  Struggles: Revisiting the RISC vs CISC debate on Contemporary ARM and x86 Architectures* by Emily Blem, Jaikrishnan Menon, and Karthikeyan Sankaralingam

#paper_the-case-for-reduced-instruction-set-architecture_dp-dd
#paper_comments-on-the-case-for-reduced-instruction-set-architecture-by-patterson-and-ditzel_dc-ws
#paper_instruction-sets-and-beyond-computers-complexity-and-controversy_rc-ch-dj-bs-ck
#paper_risc-assessment-a-high-level-language-experiment_RP-RP
#paper_power-struggles-revisiting-the-risc-vs-cisc-debate-on-contemporary-arm-and-x86-architectures_eb-jm-sk


%%
## TODO
- fact check and verify
Built using digital.exe

Open .dig files using Digital

| File Name            | Description                                                 |
| -------------------- | ----------------------------------------------------------- |
| `half_adder.dig`     | Basic combinational circuit for half-bit binary addition    |
| `full_adder.dig`     | Extends half adder to handle carry-in and produce carry-out |
| `add-sub.dig`        | Circuit that performs both binary addition and subtraction  |
| `6_ringcounter.dig`  | A 6-bit ring counter for sequential bit cycling             |
| `Opcode Decoder.dig` | Decodes instruction opcodes into control signals            |
| `Controller.dig`     | Central control logic for sequencing operations             |

Download and install Digital from the GitHub releases page:
https://github.com/hneemann/Digital/releases

Make sure all files are in the same folder to simulate and analyze the circuit

To add instructions,
  Start the simulation and click RAM to add instructions.

| Mnemonic | Opcode (4-bit) | Operand Description                         |
| -------- | -------------- | ------------------------------------------- |
| `LDA`    | `0000`         | Load accumulator from memory at `<ADDR>`    |
| `ADD`    | `0001`         | Add value at `<ADDR>` to accumulator        |
| `SUB`    | `0010`         | Subtract value at `<ADDR>` from accumulator |
| `OUT`    | `1110`         | Output accumulator value (operand ignored)  |
| `HLT`    | `1111`         | Halt execution (operand ignored)            |

  
  eg: To compute 5 + 6 - 3
  
    | Address |  Data  |
    | ------- | ------ |
    | `0x0`   | `0x09` | → `LDA 0x9` (load value at `0x9` → 5)     
    | `0x1`   | `0x1A` | → `ADD 0xA` (add value at `0xA` → 6)      
    | `0x2`   | `0x2B` | → `SUB 0xB` (subtract value at `0xB` → 3) 
    | `0x3`   | `0xE0` | → `OUT`      (output result)              
    | `0x4`   | `0xF0` | → `HLT`      (halt execution)             
    | `0x9`   | `0x05` | → data: 5                                 
    | `0xA`   | `0x06` | → data: 6                                 
    | `0xB`   | `0x03` | → data: 3                                 



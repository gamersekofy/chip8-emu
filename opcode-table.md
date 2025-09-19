# Chip-8 Opcodes

Of course, here is the information organized into a Markdown table.

| Opcode | Description | Notes |
| :--- | :--- | :--- |
| `0000` | Nop | Do nothing, progress to next opcode |
| `00E0` | Clear screen | |
| `00EE` | Return from subroutine | |
| `1NNN` | Jump to address `0xNNN` | |
| `2NNN` | Call `0xNNN` | Enter subroutine at `0xNNN`, adding current PC onto stack |
| `3XNN` | Skip if `VX == 0xNN` | |
| `4XNN` | Skip if `VX != 0xNN` | |
| `5XY0` | Skip if `VX == VY` | |
| `6XNN` | `VX = 0xNN` | |
| `7XNN` | `VX += 0xNN` | Doesn’t affect carry flag |
| `8XY0` | `VX = VY` | |
| `8XY1` | `VX |= VY` | |
| `8XY2` | `VX &= VY` | |
| `8XY3` | `VX ^= VY` | |
| `8XY4` | `VX += VY` | Sets `VF` if carry |
| `8XY5` | `VX -= VY` | Clears `VF` if borrow |
| `8XY6` | `VX >>= 1` | Store dropped bit in `VF` |
| `8XY7` | `VX = VY - VX` | Clears `VF` if borrow |
| `8XYE` | `VX <<= 1` | Store dropped bit in `VF` |
| `9XY0` | Skip if `VX != VY` | |
| `ANNN` | `I = 0xNNN` | |
| `BNNN` | Jump to `V0 + 0xNNN` | |
| `CXNN` | `VX = rand() & 0xNN` | |
| `DXYN` | Draw sprite at (`VX`, `VY`) | Sprite is `N` pixels tall, `VF` set if any pixels flipped |
| `EX9E` | Skip if key in `VX` is pressed | |
| `EXA1` | Skip if key in `VX` isn’t pressed | |
| `FX07` | `VX = Delay Timer` | |
| `FX0A` | Wait for key press, store in `VX`| Blocking operation |
| `FX15` | `Delay Timer = VX` | |
| `FX18` | `Sound Timer = VX` | |
| `FX1E` | `I += VX` | |
| `FX29` | Set `I` to address of font char in `VX` | |
| `FX33` | Store BCD of `VX` into `I` | |
| `FX55` | Store `V0` thru `VX` into RAM at `I` | Inclusive range |
| `FX65` | Fill `V0` thru `VX` from RAM at `I` | Inclusive |



```
FILE>>>|.midi_to_command
note ♦️9♦️50♦️127-70♦️in♦️ cmd:log xbox boolean A true
note ♦️9♦️50♦️127-70♦️out♦️ cmd:log xbox boolean A false

note ♦️9♦️50♦️20-127♦️in♦️ cmd:log xbox boolean A true
note ♦️9♦️50♦️0-20♦️in♦️ cmd:log xbox boolean A false

SINCO ♦️ note ♦️ c9 ♦️ n50 ♦️127-70♦️in♦️ cmd:log xbox boolean A true
SINCO ♦️ note ♦️ c9 ♦️ n50 ♦️127-70♦️ out♦️ cmd:log xbox boolean A false

MPK mini play ♦️ note ♦️ c0 ♦️ n50 ♦️127-70♦️ in♦️cmd:log xbox boolean A true
MPK mini play ♦️ note ♦️ c0 ♦️ n50 ♦️127-70♦️ out♦️ cmd:log xbox boolean A false


control ♦️ 50 ♦️ 0-50 ♦️ in ♦️ cmd:log MPK Control 50 
control ♦️ 50 ♦️ 80-127 ♦️ in♦️ cmd:log xbox boolean A false


MPK mini play ♦️ control ♦️ 50 ♦️ 0-50 ♦️ in ♦️ cmd:log MPK Control 50 
MPK mini play ♦️ control ♦️ 50 ♦️ 80-127 ♦️ in ♦️ cmd:log xbox boolean A false

## Quick Setup
# 50 ♦️ true ♦️ cmd:log quick note 50 true
# 50 ♦️ false ♦️ cmd:log quick note 50 false
#  MPK mini play ♦️ 50 ♦️ true ♦️ cmd:log quick note 50 true
#  MPK mini play ♦️ 50 ♦️ false ♦️ cmd:log quick note 50 false

```


# 6045: Inverter: Output: No current flow

报警6045，电机相关，也可能是供电问题。
客户明确说，伺服连接的电机非常小，不是应该配置的电机。
希望屏蔽报警，看看是否有电流，可能想判断伺服问题。

注：屏蔽温度等测试都具有非常大的危险性，应该明确告知客户。

如果需要屏蔽该报警，可以通过操作如下ParID。

# 866: Motor: Test mode

**Define:**

MOTOR_TEST_MODE

**Access:**

RD, WR(nCTRL)(nMOVE)

**Unit:**

**Data type:**
UDINT
**Value range:**
0 .. 1023

**Description:**  
Bit0: Phase 1 (U): Current flow test OFF  
Bit1: Phase 2 (V): Current flow test OFF  
Bit2: Phase 3 (W): Current flow test OFF  
Bit3: Phase 123 (UVW): Offset Current check OFF  
Bit5: Phase 123 (UVW): Offset current measurement @ active power stage OFF (from V2.060)  
Bit6: External bleeder: Current flow test OFF (from V2.170)  
Bit7: Internal bleeder: Current flow test ON (from V2.230)  
Bit8: External bleeder: Overcurrent monitoring OFF (from V2.230)  
Bit9: Summation current monitoring OFF (ab V2.238)
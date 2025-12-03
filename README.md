# Arithmetic-operation-using-8086
# 8086 Assembly Language Programs for Arithmetic Operations

## AIM

To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.

---

## APPARATUS REQUIRED

* Personal Computer with MASM Software

---

## 1. ADDITION

#### Algorithm

1. Initialize memory location in HL register.
2. Store 1st data.
3. Increment HL to enter 2nd data.
4. Move 2nd number to accumulator.
5. Decrement HL.
6. Add value in memory with accumulator.
7. Store result.
8. Stop.


## FLOW CHART
<img width="400" height="700" alt="image" src="https://github.com/user-attachments/assets/b5a7062d-e294-47cd-9683-a40de25e82de" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
ADD AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|       1200: 12          |        1204: 24          |
|       1201: 34          |        1205: 68          |
|       1202: 12          |        1206: 00          |
|       1203: 34          |        1207: C4          |

#### Manual Calculations

<img width="400" height="400" alt="Screenshot 2025-09-03 000224" src="https://github.com/user-attachments/assets/cf32383d-eed2-415c-bd88-4ee5508ad14d" />

## OUTPUT IMAGE FROM MASM SOFTWARE

<img width="636" height="435" alt="Screenshot 2025-09-03 000224" src="https://github.com/user-attachments/assets/3c6cf235-ffa3-4838-9079-9ff3eee057f1" />

<img width="634" height="426" alt="image" src="https://github.com/user-attachments/assets/b8383a98-c376-4a83-80cd-41af9309a70e" />

## 2. SUBTRACTION

#### Algorithm

1. Initialize memory and store 1st data.
2. Increment to get 2nd data.
3. Move 2nd data to accumulator.
4. Subtract memory content.
5. Store result.

## FLOWCHART

<img width="400" height="500" alt="image" src="https://github.com/user-attachments/assets/564c3c7a-33ce-4a1c-8920-beb5c24b9b47" />

#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
SUB AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|       1200: 12          |        1204: 00          |
|       1201: 34          |        1205: 00          |
|       1202: 12          |        1206: 00          |
|       1203: 34          |        1207: C4          |

#### Manual Calculations

<img width="400" height="400" alt="Screenshot 2025-09-03 000254" src="https://github.com/user-attachments/assets/eeadcb68-b587-4d0d-88ab-196374dbcef7" />

## OUTPUT SCREEN FROM MASM SOFTWARE

<img width="642" height="435" alt="sub" src="https://github.com/user-attachments/assets/478abf1c-629a-49a6-9681-deee45117a17" />

<img width="644" height="431" alt="Screenshot 2025-09-03 000254" src="https://github.com/user-attachments/assets/df5faece-6e38-4b07-95b0-aa4954b571b6" />


## 3. MULTIPLICATION

#### Algorithm

1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

##FLOWCHART

<img width="500" height="600" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />

#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
MUL BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|       1200: 12          |        1204: 44          |
|       1201: 34          |        1205: 51          |
|       1202: 12          |        1206: 97          |
|       1203: 34          |        1207: 0A          |

#### Manual Calculations

<img width="400" height="400" alt="Screenshot 2025-09-03 000327" src="https://github.com/user-attachments/assets/163f968d-1f20-45ad-9ad5-520b197a7454" />


## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="637" height="431" alt="Screenshot 2025-09-03 000327" src="https://github.com/user-attachments/assets/83383a2c-b7e7-4c3c-9d8c-d04460a4e9c6" />

<img width="641" height="431" alt="Screenshot 2025-08-20 160319" src="<img width="639" height="425" alt="image" src="https://github.com/user-attachments/assets/9ae10c97-edbc-406b-b257-c76dd621d860" />


## 4. DIVISION

#### Algorithm

1. Load memory location of operands.
2. Perform division.
3. Store result.

   ## FLOWCHART
   
<img width="500" height="600" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />

#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
DIV BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|       1200: 12          |        1204: 01          |
|       1201: 34          |        1205: 00          |
|       1202: 12          |        1206: 00          |
|       1203: 34          |        1207: 00          |

#### Manual Calculations
<img width="400" height="400" alt="Screenshot 2025-09-03 000353" src="https://github.com/user-attachments/assets/ce61a799-d563-4b4b-b163-785ca06a4bc3" />

## OUTPUT FROM MASM SOFTWARE

<img width="643" height="434" alt="Screenshot 2025-09-03 000353" src="https://github.com/user-attachments/assets/6a7d4e3d-d676-4479-b230-805d342c77d5" />

<img width="641" height="437" alt="image" src="https://github.com/user-attachments/assets/fb79874b-848d-48d2-9119-2bcd29ec19db" />

## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.

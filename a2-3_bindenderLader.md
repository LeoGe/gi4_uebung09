# Aufgabe 2

Phase 1: Allocation:  
	cntdwn.o : Startadresse 0x08048000 Ende: 0x08048094  
	libc.o : Startadresse 0x08048094 Ende: 0x0804856A  

Phase 2: reallocation:  
	 siehe Symboltabelle (ESTAB), alle Modul-Sätze wurden verwendet um die Adressen anzupassen.  
	PROGADDR: 08048000  
	EXECADDR: 08048000  

Speicher:  
hier kommen zuerst die T-Sätze aus cntdw.o  
08048000:	 0540    0C4050  02500100000004  
0804800C:	 0C100100000039  0C45010000000400000030  0A104500000004  
08048025:	 0B010000004D    0C02C000000090  05010804807D  
08048038: 	 080108048094    01500100000004  0410  
08048047:	 07010000001E    01500100000004  0640  
08048056:	 050100000000    08010804817E    01500100000004  
08048069:	 0C000100000001  0C100100000000  0D0100000080  
0804807D: 	 48656C6C6F20576F13100  
08048094: beginn von libc, printf
0804817E: exit
080481CE: malloc
080482D2: scanf
080484F2: free
0804846A: ende

# Aufgabe 3

Man könnte mit Hilfe der R-Datensätze die T-Datensätze von printf und exit in die Objektdatei von cntdwn hinzufügen. Dann müssten außerdem weitere M-Datensätze aus libc.o übernommen werden die diesen Bereich betreffen, damit nachher die Adressen angepasst werden können. 


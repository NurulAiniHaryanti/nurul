
ORG 000H                 
 MOV P1,#00000011B        
 MOV P0,#00000000B        
 BACK: MOV P0,#00000011B 
       JB P1.0, LABEL1   
       CLR P0.0          
       SETB P0.1          
       ACALL WAIT1      
       SJMP BACK         
LABEL1: JB P1.1, LABEL2   
        SETB P0.0        
        CLR P0.1          
        ACALL WAIT2       
        SJMP BACK         
LABEL2: SJMP BACK         
WAIT1:JNB P1.0,WAIT1      
      RET                 
WAIT2:JNB P1.1,WAIT2      
      RET                 
END     

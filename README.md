# python
def emi_cal(p,r,t):
    r=r/(12*100)
    for i in range(0,t):
        emi=(p*r*pow(1+r,t))/(pow(1+r,t)-1)
        if(i==0):
            si=(p*t*r)/100
            Bal=((p+si)-emi)
        else:
            si=(Bal*t*r)/100
            Bal=((Bal+si)-emi)
        #print("balance",Bal,si,emi)
        if (Bal<0):
            print("Balance is 0")
        else:
            print('Principal=', p, '\tBalance=', Bal, '\tEMI=',emi)
            #print("Principal\tBalance\tEMI\t",p,Bal,emi)      
    return emi

principal=int(input("Enter Principal Amount\n"))
time=int(input("Enter time in months\n"))
rate=int(input("Enter Rate of Interest\n"))
emi=emi_cal(principal,rate,time);
  

```python
# combination calculator. C(n,r) = n!/((n-r)!r!) 
# loop debugging print statements have been commmented out but left in the code for future reference
def combocalc(n,r):
    nfac = n
    rfac = r
    nsubr = n-r
    for i in range(n-1,0,-1):       #n factorial calculation
#        print("start loop nfac is now",nfac)
        nfac*=i
#        print("I is currently",i)
#        print("end loop nfac is now",nfac)
    print("Final nfac =",nfac)
    for i in range(r-1,0,-1):      #r factorial calculation
        rfac*=i
    print("Final rfac =",rfac)
    for i in range(nsubr-1,0,-1):  #n-r factorial calculation
        nsubr*=i
    print("Final nsubr =",nsubr)
    print(nfac/(rfac*nsubr))      #n!/((n-r)!r!) printed to verify correct result prior to returning value
    return nfac/(rfac*nsubr)

combocalc(12,7)


```

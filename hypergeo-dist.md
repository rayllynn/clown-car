```python
#combocalculator again but with modified output to calculate the hypergeometric distribution

# combination calculator. C(n,r) = n!/((n-r)!r!)
def combocalc(n,r):
    nfac = n
    rfac = r
    nsubr = n-r
    for i in range(n-1,0,-1):       #n factorial calculation
        nfac*=i
#    print("Final nfac =",nfac)
    for i in range(r-1,0,-1):      #r factorial calculation
        rfac*=i
#    print("Final rfac =",rfac)
    for i in range(nsubr-1,0,-1):  #n-r factorial calculation
        nsubr*=i
#    print("Final nsubr =",nsubr)
#    print(nfac/(rfac*nsubr))      #n!/((n-r)!r!)
    return nfac/(rfac*nsubr)

#Calculate hypergeometric distribution using values of variables provided below
def hypergeomcalc(a,b,k,n):
    print("The probability of selecting",k,"objects of type A is ")
    result = round((combocalc(a,k)*combocalc(b,n-k))/combocalc(a+b,n),4)
    return result

#Seek user input for variable values
try:
    print("Enter the number of elements of type A:")
    a = int(input())
    print("You have entered",a,"elements of type A.")

    print("\nEnter the number of elements of type B:")
    b = int(input())
    print("You have entered",b,"elements of type B.")

    print("\nAssuming only 2 types of elements, this gives a total of",a+b,"elements.")
    totalelements = a+b

    print("\nEnter the total number of elements you wish to choose without replacement:")
    n=int(input())

    print("\nEnter the number of elements of type A you wish to find the probability of selecting when selecting",n,"total elements:")
    k = int(input())
    print("You would like to select",k,"objects of type A.\n")
#Call hypergeo distribution function
    print(hypergeomcalc(a,b,k,n))
except TypeError:    #TypeError handling for if a user enters a non-numeric value
    print("Values must be integers.")
except Exception:              #Misc error handling
    print("An error has occurred.")


```

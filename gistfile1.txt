'''
A valid email address meets the following criteria:

It's composed of a username, domain name, and extension assembled in this format: username@domain.extension
The username starts with an English alphabetical character, and any subsequent characters consist of one or more of the following: alphanumeric characters, -,., and _.
The domain and extension contain only English alphabetical characters.
The extension is , , or  characters in length.
Given  pairs of names and email addresses as input, print each name and email address pair having a valid email address on a new line.
'''
# Enter your code here. Read input from STDIN. Print output to STDOUT
n=int(input())
email= [None]*n
check=""
for x in range(n):
    email[x]=input()
for x in range(n):
    check=email[x].split(" ")
    c=check[1]
    check=c.split("<")
    c=check[1]
    #print(c)
    check=c.split("@")
    c=check[0]
    #print(c)
    c2=check[1]
    #print(c2)
    domain=c2.split(".")
    d3=domain[0]
    ext=domain[1]
    ext=ext.split(">")
    extension=ext[0]
    #print(extension)#extension of the email id
    #print(d3)#domain of the email id
    u1=c[0]
    #print(u1)
    #print(u1.isalpha())
    #print(c)
    if(u1.isalpha()):
        l=len(c)
        usercheck=0
        for z in range(l):
            #print(c[z])
        #print(c[x]) #don't know what :P
            if (('-' in c[z]) or ('.' in c[z]) or ('_' in c[z]) or (c[z].isalnum())):
                usercheck+=1
                
            #print(c[y])
        if(usercheck==l):
            if((d3.isalpha())and(extension.isalpha())):
                    elen=len(extension)
                    if((elen==1) or (elen==2) or (elen==3)):
                        print(email[x])
     
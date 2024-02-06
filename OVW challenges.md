The challenges I worked on this time were command line system exploitation to find passwords on the system. Direction to Overthewire let’s go.

I dealt with right now ten levels of the Overthewire bandit game. To do the walkthrough of all the challenges will be fun, but I find it a little exhausting.  So I will only give here the walkthrough of the challenges that were a little confusing for me to deal with. 

The first was Level 6 —> 7.

The objective was to find the password in a file with specific characteristics:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

` `The file wasn’t somewhere precisely on the server, so the true challenge was about to find the location of the file. 

My first idea was to look in the /home repository, which contains all the files of the different users of the system.

So my first idea was to look for the file with the grep command. The listed /home repository sort many sub-repositories : bandit 0 to 23, bandit-git 1 to 6, krypton and one another.  So I build a logical expression   with the ls on the grep command 

ls -la -R | grep bandit7 | grep bandit 6

I tried with this to list all the files with the owner or group that was bandit7 or bandit6.

But it was unsuccessful.

So I head top to the root  / repository to list the files with a different command because I found out that the output of my last directory was not successful due to many permissions denied error 

![](Aspose.Words.5b806ef8-727a-4cd1-a4db-6f1d209808ff.001.png)

So with some searches, I found out that the find command gives you options to look for a file based on its owner, group and size of the file.

![](Aspose.Words.5b806ef8-727a-4cd1-a4db-6f1d209808ff.002.png)

This output is a bit confused, so I simplified it by filtering it using the dev/null file, which I used to redirect all the output errors there.

![](Aspose.Words.5b806ef8-727a-4cd1-a4db-6f1d209808ff.003.png)

With this, I was able to find the file and read its content. Done  !!


For the second challenge, Level 9 —> 10.

## <a name="_xb5yegyfgcne"></a>Level Goal
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.


Objective; To find the password, which is a string that is embedded in the data.txt file.

The data.txt file is a data file precisely, binary files.

So instinctively, I used the strings command to find the password, but the output was a little unsettled. Because I already have an idea of the password format I was looking for.  So I decided, to look for it through a different method. I then found out that I could sort out all the strings and then use grep to filter the lines with strings preceded by “=” character.

![](Aspose.Words.5b806ef8-727a-4cd1-a4db-6f1d209808ff.004.png)

![](Aspose.Words.5b806ef8-727a-4cd1-a4db-6f1d209808ff.005.png)

And there is the password.

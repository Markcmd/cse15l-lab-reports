# CSE15L
## Lab 1

### cd-Test
![cd-Test](cd-Test.png)

+ ```
  [user@sahara ~]$ cd
  [user@sahara ~]$
  ```

1. The working directory:  `/home`
2. Output explanation: because there is no argument for the cd command, no change in the directory.
3. Meaning to have no argument: First, Note that the above statement for "Output explanation:" is incomplete. No argument means going back to the   user's home directory. (Find the feature of cd while answering the question.)
    ```
    [user@sahara ~]$ cd lecture1
    >[user@sahara ~/lecture1]$ cd
    >[user@sahara ~]$ 
    ```
4. Is output error? why? : No, Because it meant to back to the home directory, so it looks like there is no change. And no output
  
+ ```
  [user@sahara ~]$ cd lecture1
  [user@sahara ~/lecture1]$
  ```
1. The working directory: `/home`
2. Output explanation: The working directory changed from `/home` to `/home/lecture1`
3. Is output error? why? : No, the directory changed to `/home/lecture1` which is what I want it to do. And the syntax is correct. And there is no output.

+ ```
  [user@sahara ~/lecture1]$ cd Hello.java
  bash: cd: Hello.java: Not a directory
  [user@sahara ~/lecture1]$ 
  ```
1. The working directory: `/home/lecture1`
2. Output explanation: The cd command expects a valid directory as an argument or no argument, but Hello.java is a file, therefore error warning comes out.
3. Is output error? why? : Yes, as mentioned in 2. above, it outputs a `bash:` error says Hello.java is not a valid directory.

### ls-Test
![cd-Test](ls-Test.png)

+ ```
  [user@sahara ~]$ ls
  lecture1
  [user@sahara ~]$   
  ```
1. The working directory: `/home`
2. Output explanation: The output means there is directory lecture1 in the current directory which is `/home`.
3. Meaning to have no argument: It means it will list all directories and files in the current directory.
4. Is output error? why? : No, because there can be no argument or directory as an argument in ls command.

+ ```
  [user@sahara ~]$ ls lecture1
  Hello.class  Hello.java  lecture1  messages  README
  [user@sahara ~]$
  ```
1. The working directory:  `/home`
2. Output explanation: The output listed every directory and file in the directory `/home/lecture1`
3. Is output error? why? : No, the argument lecture1 exists in the current working directory as a directory, and it is a valid directory.

+ ```
  [user@sahara ~]$ ls Hello.java
  ls: cannot access 'Hello.java': No such file or directory
  [user@sahara ~]$
  [user@sahara ~]$ cd lecture1
  [user@sahara ~/lecture1]$
  ```
  I made a mistake here, there is no file in the current working directory, so it gave me an error. And then I moved to the new directory `/home/lecture1`.
+ ```
  [user@sahara ~/lecture1]$ ls Hello.java
  Hello.java
  [user@sahara ~/lecture1]$
  ```
1. The working directory: `/home/lecture1`
2. Output explanation: It outputs the file name, which means the file is in the current directory.
3. Is output error? why? : No, the reason is the same as above 2.. And the syntax is correct. 
Question: So, is the reason why this feature of ls is made to check if a certain file is in the current directory?

### cat-Test
![cd-Test](cat-Test.png)
![cd-Test](cat-Test.png)

+ ```
  [user@sahara ~]$ cat
  lecture1
  lecture1
  lecture1
  lecture1
  ^Z
  [2]+  Stopped                 cat
  [user@sahara ~]$ 
  ```
1. The working directory:  `/home`
2. Output explanation: Initially, there was no output. After I entered the first "lecture1" it outputs just what I entered which is "lecture1". Until I pressed the "ctrl + z" it stopped.
3. Meaning to have no argument: It seems like It allows me to enter something after the cat command without an argument, and it will do nothing but output what I entered.
4. Is output error? why? : No, because an error warning did not appear.

+ ```
  [user@sahara ~]$ cat lecture1
  cat: lecture1: Is a directory
  [user@sahara ~]$
  ```
1. The working directory:  `/home`
2. Output explanation: Directory cannot be the argument of the cat command. Because the error came out.
3. Is output error? why? : Yes, a directory cannot be the argument of the cat command.

+ ```
  [user@sahara ~]$ cd lecture1
  [user@sahara ~/lecture1]$ cat Hello.java
  import java.io.IOException;
  import java.nio.charset.StandardCharsets;
  import java.nio.file.Files;
  import java.nio.file.Path;

  public class Hello {
    public static void main(String[] args) throws IOException {
      String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
      System.out.println(content);
  }
  }[user@sahara ~/lecture1]$
  ```

1. The working directory: `/home/lecture1`
2. Output explanation: The cat command outputs the contents in the file.
3. Is output error? why? : No, the command executed successfully.

   ```
   [user@sahara ~/lecture1/messages]$ cat en-us.txt
   Hello World!
   [user@sahara ~/lecture1/messages]$
   ```
   Tried different types of files. It still works.


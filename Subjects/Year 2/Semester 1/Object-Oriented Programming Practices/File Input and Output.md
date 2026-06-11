---
aliases:
  - File I/O
tags:
  - Notes
  - Java
Date: 2024-09-16
Completion: true
obsidianUIMode: preview
---
Every data created and stored in a program is lost once the program terminates. To solve this issue, you would have to save these data into a permanent storage. When opening a file, an [[Exception Handling|exception]] should be thrown. 

# Text files
Reading and writing into a text file requires encoding and decoding. Writing into a text file requires encoding the Unicode into a file specific format while reading from a text file requires decoding the file specific format into Unicode. 
## Writing
To write data into a text file, `PrintWriter` object is used.

```java
PrintWriter outputFile = new PrintWriter('studentData.txt');
```

You would write into the file with the same way you display output to the console
```java
outputFile.println("Jimmy Ding");
// print("Jimmy Ding"); works fine too
// printf("Jimmy Ding"); works fine too
```

>[!WARNING] Erasing content
>This way of writing into a file will erase the content in the file before writing anything new into the file.

To prevent the erasure, we can use `FileWriter` object.

```java
FileWriter file = new FileWriter("studentData.txt");
PrintWriter outputFile = new PrintWriter(file);

outputFile.println("Jimmy Ding");
```
## Reading
To read from a file, you would use the `Scanner` class. *Sounds familiar?*<br>All you have to do is add the URL of the database into the `Scanner` constructor. 

```java
Scanner fileReader = new Scanner("studentData.txt");

// or
File studentfile = new File("studentData.txt");
Scanner fileReader = new Scanner(studentFile);
```

Once again, reading from the file is the same as receiving inputs from the user.
```java
int age;
age = fileReader.nextInt(); // nextInt() returns the next token as int
```

To check if the file has reached the end, `.hasNext()` method can be used.

```java
File file = new File("studentData.txt");
Scanner fileReader = new Scanner(file);

while (fileReader.hasNext()){
	String str = fileReader.nextLine();
	System.out.println(str);
}
fileReader.close();
```

>[!REMINDER]
>Remember to close the files after opening them.

The scanners breaks its input into tokens delimited by delimiters. By default the delimiters are whitespaces. That's why your input is read word for word instead of the whole line (*if your line has whitespaces between each word and you're not using `nextLine()`*)

You can set new patterns for delimiters with `useDelimiter(String regex)`. 

# Binary Files
Sometimes, storing data in their binary format is more efficient than storing them as texts. Binary I/O does not require conversions. When a byte is written into a file, the original byte is copied into the file and when you read from the file, the exact byte is returned. 

Reading and writing from binary files are largely similar to reading and writing from text files. 
## Writing
In writing, `FileOutputStream` and `DataOutputStream` are used alongside each other.

```java
FileOutputStream fileOutput = new FileOutputStream("studentData.dat");
DataOutputStream dataOutput = new DataOutputStream(fileOutput);
```

To write into a file, these following methods are used:

```java
dataOutput.writeInt(5);
dataOutput.writeDouble(5.5);
dataOutput.writeBoolean(false);
dataOutput.writeChar('5');
dataOutput.writeChars("Five");
dataOutput.writeUTF("Five"); // UTF-8 coding
dataOutput.writeByte(7);
```

## Reading 
In reading, `FileInputStream` and `DataInputStream` are used alongside each other.

```java
FileInputStream fileInput = new FileInputStream("studentData.dat");
DataInputStream dataInput = new FileInputStream(fileInput);
```

To read a file, these following methods are used:

```java
int     x = dataInput.readInt(5);
double  x = dataInput.readDouble(5.5);
boolean x = dataInput.readBoolean(false);
char    x = dataInput.readChar('5');
String  x = dataInput.readUTF("Five"); // UTF-8 coding
byte    x = dataInput.readByte(7);
```

The order of reading data has to follow the same format in which they were written. If names are written in UTF-8, the names have to be read with `readUTF()`. 

If the data is written with `writeChars()`, the data has to be read with `readChar()`

In binary file, checking for the end of file is different; one way to do it is by using EOF flagging. 

```java
import java.io.*;

public class Main{
	public static void main(String[] args) throws IOException{
		int number; 
		boolean endOfFile = false;
		
		FileInputStream inStream = new FileInputStream("numbers-go-brr.dat");
		DataInputStream dataReader = new DataInputStream(instream);
		
		while(!endOfFile){
			try{
				number = dataReader.readInt();
				System.out.println(number);
			}
			catch(IOException e){
				endOfFile = true;
			}
		}
		dataReader.close();
	}
}
```

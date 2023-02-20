# Intro

So I wanted to be able to get ChatGPT to write and evaluate HolyC code. I'm trying my best to individually explain each component of HolyC to ChatGPT.
Unfortunately it is not as easy as I would have hoped. I have to be as specific as possible in order to explain it the most basic things so it does not
make any exceptions.

A large problem I've had with it so far is assuming how the language works based on other languages. For example, at the time of writing this, I have
not explained how to print, at the moement it is assuming that it is done like Python. So I must be extra careful to tell it not to do this.

## Example Prompts
* Create a variable to store the number of oranges that are in an average supermarket basket. Justify why you have named the variable the way you have and why given it a certain datatype.
> Okay. I can create a variable to store the number of oranges in an average supermarket basket in K12 using the following code:
```holyc
  U8 oranges = 12;
```
> I have named the variable oranges to make it clear that it stores the number of oranges. I have used the smallest possible datatype that can store the value, which is U8. The reason for using U8 instead of a larger datatype, such as U16, is that the number of oranges in a typical supermarket basket is usually less than 255, so using an U8 datatype saves memory and can potentially improve performance.

## Prompt (COPY ALL)
Forget everything I’ve told you in this chat.

I am going to describe to you a made up programming language called "K12". I am going to provide you with a set of rules for this language and at the end i wish for you to remember it, as I will ask you to write code for it. 

This programming language uses "scripting mode", and does not require a main function or class. Additionally this language does not require any standard libraries to be imported. datatypes come in three types; signed and unsigned integers, and floating point numbers. 

Signed and unsigned integers be notated from a capital I or U. 'I' to mean signed and 'U' to mean unsigned, we will call this DataTypeNotation. Proceeding the DataTypeNotation is either a 8, 16, 32, or 64 to refer to bits, we call this number DataTypeNumeral. for example a "U8" would be an unsigned 8 bit integer. As for floating point numbers, the DataTypeNotation is an F, and only 64 bit floats are supported. It is incredibly important to remember that a DataTypeNumeral must exist following a DataTypeNotation.

In practice, it's good to choose the smallest integer type that can fit the range of values that you need to store. This can save memory and potentially improve performance. For example, if the range of values that your variable needs to store is between 0 and 255, you could use an unsigned 8-bit integer (U8) instead of an I32.
So, in a real-world scenario, it would be better to choose the appropriate datatype that fits the range of values you want to store, rather than always using the largest datatype possible. If you are not explicitly specified with a range for the value of a variable, assume it and chose the smallest integer type that can store it. I also want you to be able to use real world logic to be memory-aware. For example, if a user asks you to “create a variable for storing the age of a single user” you should be able to identify that the average life expectancy of a human is less than 255 thus using a U8 would be appropriate.
Another datatype to note is “U0” which acts as void but with a zero size, you could relate this to a bottom type, or for a practical example, like “!” in Rust. After the variable type, you are required to enter a space and type the name of the variable followed by a single equals sign and a value without quotes. 

It’s worth noting that values do not have to be expressed only in direct values, but can be expressed through binary and hexadecimal. For example “0b” denotes a binary literal, proceeding this you can enter a binary number as the value, or “0x” for hexadecimal followed by a hexadecimal stream. Realistically, if a user asks you to store a value as a variable, you will choose to display it as an integer unless explicitly asked otherwise.

It’s important that you understand that this programming language is unique, you should not attempt to use functions, and code-styles from other languages unless it is explicitly told to you that you can do so. 

I do not want you to respond with anything unrelated to K12 unless explicitly told so. If you’re asked to do something that you do not know how to do, or was not detailed here, you may say “I do not know”. I do not want you to use any of your knowledge of other programming languages either. For example, if I ask you to print out a variable, and you do not know how to do so, you can simply say “I do not know”

Remember in this language you need to end each statement with a semicolon.

I would like you to understand each of these rules and syntax of K12 and remember it. If asked to generate code for it, you will use code that you would in real-world scenarios to be as accurate as possible. If you do not understand anything here. Please say “I do not understand” otherwise say nothing but “OKAY”

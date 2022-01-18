# Java-JSON-validator
A quaint utility that can validate a JSON file by uploading and checking a file, or analyzing the text itself and highlighting the problem line.

UPDATE Jan. 18 2022: Edited MainClassJSONValidator and JSONTextCompare class files to get rid of second main method in the latter of those files. Now the program will only execute from the main class alone, and it is possible to create a runnable JAR file that works from this point forward.

UPDATE Oct. 19 2021: POM.XML file added to the content of the project, as it was accidentally missing before, for anyone who might've cloned it already.

The MainClassJSONValidator class will load the main interface that will allow you to load a file into the interface to check if it is valid, or it has an error in it. As it will only return the location of the next error, repeat the validation process until the output says "JSON file is valid!".

THe JSONTextCompare class is a subclass that allows you to copy in JSON code for the same purpose and it will highlight the offending line and output it just as if you are checking a file. Similarly, it will only highlight the next error in the text, so repeat until the output says "JSON file is valid!".

The text validation has two methods to avalidate the code, which differ in the highlight output due to the implementation. The commented out method is a bit less efficient, because it counts characters in the multiline string in the file to match the location of the error, whereas the second method is using the imported RXTextUtilities class (https://tips4java.wordpress.com/2008/10/26/text-utilities/) to more efficiently find the start of the line, based on the line recovered from the error statement.

The pom.xml file houses the dependencies, as this was initially composed as a Maven project. It usees the Jackson JSON library for working through an uploaded file or JSON text.

The functionsClass class is rsponsible for validating the JSON file as valid, or not, and then extracting the line and character number by splitting the error statement and then passing those values back to the JSONTextCompare class to both display the error and produce the required highlighting.

The Results class is a Getter/Setter class for returning the erroring line and column as a statemetent, besides doing the same for the line and column numbers when they are used to highlight the proper location in the text validation part of the program.

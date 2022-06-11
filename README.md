# cmd
My first project in C#
## sample cmd program
When running, you can use the following commands in this program:
* create --file <file name>
* create --dir <directory name>
* delete --file <file name>
* delete --dir <directory name>
* help
* exit

##code
```c#
using System.IO;
using System;

namespace CMD{
    class  CMD{
      static void Main(string[] arg){
        while (true){
          String command=Console.ReadLine();
          String[] commandSplit= command.Split(" ");
          if (commandSplit[0]=="create"){
            if(commandSplit[1]=="--dir"){
              String dir =$@"./{commandSplit[2]}";
              if(!Directory.Exists(dir)){
                Directory.CreateDirectory(dir);
                Console.WriteLine($"successfully directory created");
                }
              else{
                Console.WriteLine($"Directory already exist!");
                }}
                  else if(commandSplit[1]=="--file"){
                    String fileName =$@"./{commandSplit[2]}";
                    if(!File.Exists(fileName)){
                      File.Create(fileName);
                      Console.WriteLine($"successfully File created");
                    }
                    else{
                      Console.WriteLine($"File already exist!");
                    }
                   }
                 }
               else if (commandSplit[0]=="delete"){
                   if(commandSplit[1]=="--dir"){
                     String dir =$@"./{commandSplit[2]}";
                    if(Directory.Exists(dir)){
                        Directory.Delete(dir);
                        Console.WriteLine($"successfully directory deleted");
                    }
                    else{
                         Console.WriteLine($"No directory Found!");
                    }
                   }
                   else if(commandSplit[1]=="--file"){
                     String fileName =$@"./{commandSplit[2]}";
                    if(File.Exists(fileName)){
                        File.Delete(fileName);
                        Console.WriteLine($"successfully File deleted");
                    }
                    else{
                         Console.WriteLine($"No File Found!");
                    }
                   }
                 }
                 else if (commandSplit[0]=="help"){
                    Console.WriteLine("_________________________________________________________\n\n  CMD C# PROJECT\n_________________________________________________________");
                    Console.WriteLine("\t create       |\t you can create file/directory");
                    Console.WriteLine("\t delete       |\t you can delete file/directory");
                    Console.WriteLine("_________________________________________________________");
                    Console.WriteLine("\t create --dir {directory name} |  you can create directory");
                    Console.WriteLine("\t delete --dir {directory name} |  you can delete directory");
                    Console.WriteLine("\t create --file {File name}     |  you can create file");
                    Console.WriteLine("\t delete --file {File name}     |  you can delete file");
                    Console.WriteLine("_________________________________________________________");
                    Console.WriteLine("\t exit         |\t you can exit from CMD Program");
                 }
                 else if (commandSplit[0]=="exit"){
                  break;
                 }
             
                 else{
                    Console.WriteLine("Wrong command! use help command");
                 }  
            }
           }
        }
}
```



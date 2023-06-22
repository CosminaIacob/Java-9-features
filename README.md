
# Java-9-features
https://www.youtube.com/watch?v=NJY-D9JLLdQ
## 1. REPL JShell
REPL = Read Eval Print Loop
<li> it helps you write simple code and test it in the cmd
<li> open cmd
<li> run jshell  command to enter the jshell 

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/e2e74b1e-1ea7-47ee-9388-a99c170a3e6a)
<li> run /help command to see  all the commands you can run in j shell

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/728bf176-aee2-4961-b3a3-e179f3f44987)
<li>you can directly print something from the cmd, declare and initialize variables or operations</li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/55fb74eb-2d00-4a7b-975e-047b68e904b0)
<li>run /list command to see all the commands you already executed</li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/ad6a22b4-6c4a-4c3d-b49c-4c93b99d6094)
<li>you can also create methods and call them </li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/821776dd-b75b-4316-bdcf-125598266bf3)
<li>if we run again the /list command we will see that the entire function that we defined is being referred to by a single line identifier: </li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/53329362-c106-49e8-9e8f-dc86b5872ac4)
<li>J shell is not meant to create projects. The main intent is to get a prompt response when you want to check if the logic of the code or the output is correct or not.</li>
<li>we can edit the code that we have already executed with /edit command followed by the identifier of the line and an edit pad is opened</li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/e7ab8bc4-0fe1-430d-8c4b-b7034e408a36)
<li>after you edit what you need, Accept->Exit and call the method again </li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/9ac82a41-1432-44cd-96df-94da014dd4f5)
![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/87443d2f-cdb9-4afb-ad40-dc8137f2d4bf)
<li>use /exit command to exit from J shell </li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/6e5347d7-6f27-4682-9f11-6b404cf765fd)
<li>you’re always in a complete loop: you first take an input and read it then you evaluate to see if it is correct, you print it and the loop keeps running around </li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/99b2751e-21e0-405b-ad47-2e2e3ff20b7b)

## 2. Collection Factory Methods

<li>Java 9 has added new static factory methods on list, set, and map interfaces</li>
<li>this makes it easier to create immutable instances of these collections</li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/39fb66e3-90a3-4c2d-adf4-e7fad71974ba)

<li> **Set** is an interface that extends the collection class and is an unordered collection of objects in which duplicate values cannot be stored</li>
<li> Create a set before and after Java 9: </li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/f1282dac-8cbc-4ccd-836f-a76be08a62ac)

<li>List is a sub-interface of the collection class and it contains methods to insert or delete elements on an index basis</li>













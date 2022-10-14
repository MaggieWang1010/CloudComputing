# Pi Calculate

## Formular Overview
![image](https://user-images.githubusercontent.com/55336314/195229693-78c64daf-a6e1-412d-a873-58d9b1d7ff07.png)
(x - center_x)2 + (x - center_x)2 compare r2
Inside: if compare is <
Outside: if compare is >
On the circle: if compare is =
![image](https://user-images.githubusercontent.com/55336314/195230106-07fe71f0-f0b1-4868-9808-f797b1902dc4.png)

## Implementaion 
Step 1: Generate an input file to the Pi MapReduce program
Step 1.1: Create a regular Java program which accepts two command line arguments.
R: The radius
N: The number of (x, y) pairs to create The Java program then randomly generates N pairs of (x, y) and displays them on the standard output. Step 1.2: Run the program created in Step 1.1 and save the result in a file. The file is the input to Step 2's Pi MapReduce program.
Step 2: Create a MapReduce program to calculate the numbers of inside darts and outside darts.
Step 3: Use the file generated in Step 1.2 as the input to execute the MapReduce program created in Step 2
Step 4: Calculate Pi in the driver program based on the numbers of inside darts and outside darts.

This project use Hadoop environment of GCP
## Prepare input data
  $ mkdir PiCalculation
  $ cd PiCalculation
  $ vi GenerateRandomNumbers.java
  $ javac GenerateRandomNumbers.java
  $ java -cp . GenerateRandomNumbers
Input data will store in PiCalculationInput

## Setup passphraseless ssh
Now check that you can ssh to the localhost without a passphrase:

  $ cd hadoop-3.3.4/
  $ ssh localhost
If you cannot ssh to localhost without a passphrase, execute the following commands:

  $ ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa
  $ cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
  $ chmod 0600 ~/.ssh/authorized_keys
## Make the HDFS directories required to execute MapReduce jobs(Copy input data to HDFS)
  $ cd ..
  $ cd hadoop-3.3.4/
  $ bin/hdfs namenode -format
  $ sbin/start-dfs.sh
  $ wget http://localhost:9870/
  $ bin/hdfs dfs -mkdir /user
  $ bin/hdfs dfs -mkdir /user/mwang
  $ bin/hdfs dfs -mkdir /user/mwang/picalculate
  $ bin/hdfs dfs -mkdir /user/mwang/picalculate/input
  $ bin/hdfs dfs -put ../PiCalculation/PiCalculationInput /user/mwang/picalculate/input
If you can not copy input into hadoop dictionary, please restart the virtual machine.

## Prepare code
Build PiCalculation java file
  $ cd /hadoop-3.3.4
  $ vi PiCalculation.java      
Compile PiCalculation.java and create a jar
  $ bin/hadoop com.sun.tools.javac.Main PiCalculation.java
  $ jar cf wc.jar PiCalculation*class  

## Run
Execute
  $ bin/hadoop jar wc.jar PiCalculation /user/mwang/picalculate/input /user/mwang/picalculate/output5
Output
  $ bin/hdfs dfs -ls /user/mwang/picalculate/output5
  $ bin/hdfs dfs -cat /user/mwang/picalculate/output5/part-r-00000 
Stop
  $ sbin/stop-dfs.sh
  
## Test Result
Test Case:

How many random numbers to generate: 10000 Radius = 200
![image](https://user-images.githubusercontent.com/55336314/195896605-94bb6973-432d-40bf-88ee-24d2afa1ada6.png)


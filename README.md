# hadoop-mipr
To run hadoop-mipr RGB to gray conversion experiments, follow the guidelines given below:
Download mipr framework from the link: https://github.com/sozykin/mipr
Extract and place ii in your home directory
Run the following command:

hadoop fs -copyFromLocal SampleImages

(SampleImages being the local FS folder where the images are stored)
This command will create the folder SampleImages in HDFS.

Note: Don’t create a folder in HDFS first (or providing the new HDFS folder in above command) and then run the above command. Doing so will not properly execute the program.

You can see whether the images are loaded properly or not by invoking Hadoop File Explorer:
http://localhost:50070/explorer.html#/

Run following command in terminal from the path of  mipr-core-0.1-jar-with-dependencies.jar 
(In our case, it was /mipr/core_package/target)

hadoop jar mipr-core-0.1-jar-with-dependencies.jar experiments.Img2Gray SampleImages mipr1output

Download the converted images to your local file system from mipr1output folder by accessing Hadoop File Explorer

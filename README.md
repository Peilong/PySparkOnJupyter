# Install PySpark on Jupyter notebook 

*Note that this tutorial is intended for the installation on Ubuntu Linux version 18.04. Installation on other OSes may vary.*

1. To install Spark, make sure you have Java 8 or higher installed on your computer [link](https://docs.oracle.com/javase/8/docs/technotes/guides/install/install_overview.html). Then, visit the Spark downloads [page](http://spark.apache.org/downloads.html). Select the latest Spark release 2.4.6, a prebuilt package for Hadoop 2.7, and download it directly.

Unzip it and move it to your /opt folder (on other system, you may want to choose another folder). Change the extracted folder to a shorter folder name of your choice, in this example, "spark-2.4.6". 
```sh
$ tar -xzf spark-2.4.6-bin-hadoop2.7.tgz
$ mv spark-2.4.6-bin-hadoop2.7 /opt/spark-2.4.6
```

2. Create a symbolic link "/opt/spark", This way, you will be able to download and use multiple Spark versions - just link to the version you like. 
```sh
$ ln -s /opt/spark-2.4.6 /opt/spark̀
```

3. Configure your shell profile. On ubuntu the default shell is bash, so we have to edit `~/.bashrc`. Add the following lines to the bash profile on Ubuntu (on Windows, you need to add the following to system PATH). 

```sh
export SPARK_HOME=/opt/spark
export PATH=$SPARK_HOME/bin:$PATH
export PYSPARK_DRIVER_PYTHON=jupyter
export PYSPARK_DRIVER_PYTHON_OPTS='notebook'
```

4. Assuming you have Anaconda 3 installed, now install PySpark with Conda package manager.
```sh
conda install -c conda-forge pyspark
```


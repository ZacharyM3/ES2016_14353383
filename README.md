##Description
###Introduction
> The distributed operation layer (DOL) is a software development framework to program parallel applications. The DOL allows to specify applications based on the Kahn process network model of computation and features a simulation engine based on SystemC. Moreover, the DOL provides an XML-based specification format to describe the implementation of a parallel application on a multi-processor systems, including binding and mapping.
![DOL](https://raw.githubusercontent.com/ZacharyM3/MarkdownPhotos/master/DOL.png)	
***
##How to install
### Setup VMware
1. Download VMware
Download VMware from its official website
2. Install necessary enviroment
	* Ant
	* jdk
	* unzip software


###Unzip files
1. add folder
`sudo mkdir dol` 
2. unzip dol
`sudo unzip dol_ethz.zip -d dol`
3. unzip systemc
`sudo tar -zxvf systemc-2.3.1.tgz`

###Compile systemc
Code:
```
cd systemc-2.3.1
sudo mkdir objdir
cd objdir
sudo ../configure CXX=g++ --disable-async-updates
```

###Compile systemc
Code:
`sudo make install`
`sudo pwd`
*<small>Here comes the path of working</small>*

####Compile dol
1. Get into file **dol** and then find file **build_zip.xml**
2. Find following code
```
<property name="systemc.inc" value="YYY/include"/>
<property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>
```
3. replace **YYY** into the path of working last step
*(Warining: change lib-linux into lib-linux64 if working on 64bits machine)*

4. Then compile
`sudo ant -f build_zip.xml all`

###Test
Run the first example 
`cd build/bin/main`
`ant -f runexample.xml -Dnumber=1`
Success Shows Below:
![successbuild](https://raw.githubusercontent.com/ZacharyM3/MarkdownPhotos/master/Build_success.png)

##Thoughts
It's the first time to use Markdown and Git to finish a lab.
Markdown is indeed an awesome language to composing an article which can achieve a good visual effect easily.
Git is a good tools to control versions and I hope I can learn more about them.

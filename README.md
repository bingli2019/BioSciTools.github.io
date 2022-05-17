## BioSciTools

### 1. BioSciTools Description
**BioSciTools: (Bioinformatics Science Tools)**, a desktop program developed based on `Java 11`, aims to make new exploration and contribution to the development of bioinformatics, and realize data analysis and visualization in the fields of **sequence analysis**, **multimomics (transcriptomics, genomics, protein omics, metabonomics, single cell)**, **microbiology**, **clinical**, etc. The program inherits the excellent interactive components, perfect analysis function and beautiful operation interface of **HiPlot** (https://hiplot.com.cn), which I developed based `VUE.js` and `Node.js`, etc.

### 2. Meta Information
**BioSciTools Source Code Github Repository:** **_https://github.com/BioSciTools/BioSciTools_**

**BioSciTools Release Repository:** **_https://github.com/BioSciTool/BioSciTools.github.io_**

**BioSciTools Release Website:** **_https://bioscitools.github.io_**

**BioSciTools-v1.0.9 Download (Github):** **_https://hub.fastgit.xyz/BioSciTools/BioSciTools.github.io/releases/download/v1.0.9/BioSciTools-v1.0.9.exe_**

### 3. BioSciTools Usage
Download new version from **BioSciTools Release Website** or **BioSciTools Release Repository:**.

No need: `Java 11.0` environment and `R 4.20` language environment, and the sample files are stored in the examples directory.

![BioSciTools CorPlot App](https://benben-miao.gitee.io/image-cloud/BioSciTools/tool_CorPlot.png)

### 4. BioSciTools Develop
```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>benbenmiao</groupId>
    <artifactId>BioSciTools</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <maven.compiler.source>11</maven.compiler.source>
        <maven.compiler.target>11</maven.compiler.target>
    </properties>
    <dependencies>
        <dependency>
            <groupId>org.openjfx</groupId>
            <artifactId>javafx-controls</artifactId>
            <version>18</version>
        </dependency>
        <dependency>
            <groupId>org.openjfx</groupId>
            <artifactId>javafx-fxml</artifactId>
            <version>18</version>
        </dependency>
        <dependency>
    		<groupId>org.openjfx</groupId>
    		<artifactId>javafx-web</artifactId>
    		<version>18</version>
		</dependency>
		<dependency>
		    <groupId>org.openjfx</groupId>
		    <artifactId>javafx-media</artifactId>
		    <version>18</version>
		</dependency>
		<dependency>
		    <groupId>org.openjfx</groupId>
		    <artifactId>javafx-swing</artifactId>
		    <version>18</version>
		</dependency>
        <dependency>
		    <groupId>org.biojava</groupId>
		    <artifactId>biojava-core</artifactId>
		    <version>6.0.5</version>
		</dependency>
		<dependency>
		    <groupId>org.biojava</groupId>
		    <artifactId>biojava-structure</artifactId>
		    <version>6.0.5</version>
		</dependency>
		<dependency>
		    <groupId>org.biojava</groupId>
		    <artifactId>biojava-ontology</artifactId>
		    <version>6.0.5</version>
		</dependency>
		<dependency>
		    <groupId>org.biojava</groupId>
		    <artifactId>biojava-ws</artifactId>
		    <version>6.0.5</version>
		</dependency>
		<dependency>
		    <groupId>org.biojava</groupId>
		    <artifactId>biojava-structure-gui</artifactId>
		    <version>6.0.5</version>
		</dependency>
		<dependency>
		    <groupId>org.biojava</groupId>
		    <artifactId>biojava-aa-prop</artifactId>
		    <version>6.0.5</version>
		</dependency>
		<dependency>
		    <groupId>org.biojava</groupId>
		    <artifactId>biojava-survival</artifactId>
		    <version>6.0.5</version>
		</dependency>
		<dependency>
		    <groupId>org.biojava</groupId>
		    <artifactId>biojava-protein-disorder</artifactId>
		    <version>6.0.5</version>
		</dependency>
		<dependency>
		    <groupId>org.biojava</groupId>
		    <artifactId>biojava-genome</artifactId>
		    <version>6.0.5</version>
		</dependency>
		<dependency>
		    <groupId>org.biojava</groupId>
		    <artifactId>biojava-modfinder</artifactId>
		    <version>6.0.5</version>
		</dependency>
      	<dependency>
    		<groupId>org.rosuda.REngine</groupId>
   			<artifactId>Rserve</artifactId>
    		<version>1.8.1</version>
		</dependency>
		<dependency>
    		<groupId>org.rosuda.REngine</groupId>
    		<artifactId>REngine</artifactId>
    		<version>2.1.0</version>
		</dependency>
    </dependencies>
    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.8.0</version>
                <configuration>
                	<!-- mvn clean install -->
                	<!-- mvn clean package -->
                    <release>11</release>
                </configuration>
            </plugin>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-assembly-plugin</artifactId>
                <version>3.2.0</version>
                <!-- mvn clean install -->
                <executions>
                    <execution>
                        <id>make-assembly</id>
                        <phase>package</phase>
                        <goals>
                            <goal>single</goal>
                        </goals>
                    </execution>
                </executions>
                <configuration>
                    <archive>
                        <manifest>
                            <mainClass>benbenmiao.BioSciTools.AppLaunch</mainClass>
                        </manifest>
                    </archive>
                    <descriptorRefs>
                        <descriptorRef>jar-with-dependencies</descriptorRef>
                    </descriptorRefs>
                </configuration>
            </plugin>
            <plugin>
                <groupId>org.openjfx</groupId>
			    <artifactId>javafx-maven-plugin</artifactId>
			    <version>0.0.8</version>
			    <configuration>
			    	<!-- mvn clean javafx:run -->
			        <mainClass>benbenmiao.BioSciTools.App</mainClass>
			    </configuration>
            </plugin>
        </plugins>
    </build>
</project>
```


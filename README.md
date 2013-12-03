maven-repo
==========

maven repository

To use this repository add to your pom.xml:

        <repositories>
            <repository>
                <id>komarevsky-releases</id>
                <url>https://github.com/komarevsky/maven-repo/tree/master/releases</url>
            </repository>
        </repositories>

_ _ _

To add new artifact to this repository:
* clone maven-repo project
* add the following

        <distributionManagement>
            <repository>
                <id>repo</id>
                <url>https://github.com/komarevsky/maven-repo/tree/master/releases</url>
            </repository>
            <snapshotRepository>
                <id>repo-snapshot</id>
                <url>https://github.com/komarevsky/maven-repo/tree/master/snapshots</url>
            </snapshotRepository>
        </distributionManagement>

to pom.xml of project you want to add to repository
* deploy your project in the following way

        mvn -DaltDeploymentRepository=repo::default::file://d:\\Work\\projects\\my\\maven-repo\\releases clean deploy

or

        mvn -DaltDeploymentRepository=repo-snapshot::default::file://d:\\Work\\projects\\my\\maven-repo\\snapshots clean deploy

where d:\\Work\\projects\\my\\maven-repo is path to cloned maven-repo
* add, commit and push maven-repo
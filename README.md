Maven SpotBugs 
---

cbonoz/maven-spotbugs

Circle CI Orb for uploading SpotBugs artifacts from your java maven projects.

### How to Use:
* Ensure the SpotBugs plugin is added to the pom.xml of your maven project: https://spotbugs.readthedocs.io/en/latest/maven.html
* Include the cbonoz/maven-spotbugs orb in your config.yml
* Run: `spotbugs/run` in your build.

An artifact with the spotbugs report should now be available in your CircleCI artifacts container.

### Example Config
<pre>
examples:
  simple_upload:
    description: Upload a SpotBugs artifact from a maven project in the `src` home directory that has SpotBugs specified in the pom.
    usage:
      version: 2.1
      orbs:
        spotbugs: cbonoz/maven-spotbugs@0.0.2
      workflows:
        main:
          jobs:
            - spotbugs/run:
                source_directory: src
                spotbugs_results_path: src/target/site
</pre>

### TODO: 

* Automatically pull spotbugs from maven, ex:
<pre>
    mvn org.apache.maven.plugins:maven-dependency-plugin:2.4:get -DartifactId=com.github.spotbugs -DgroupId=spotbugs-maven-plugin -Dversion=3.1.11
</pre>
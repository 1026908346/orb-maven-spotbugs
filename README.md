Circle CI Orb
---

Upload spotbug artifacts on your maven projects.

### How to use:
* Ensure the SpotBugs plugin is added to the pom.xml of your maven project: https://spotbugs.readthedocs.io/en/latest/maven.html
* Include the cbonoz/maven-spotbugs orb in your config.yml
* Run: `spotbugs/run` in your build.

An artifact with the spotbugs report should now be available in your CircleCI artifacts container.

### TODO: 

* Automatically pull spotbugs from maven, ex:
<pre>
    mvn org.apache.maven.plugins:maven-dependency-plugin:2.4:get -DartifactId=com.github.spotbugs -DgroupId=spotbugs-maven-plugin -Dversion=3.1.11
</pre>
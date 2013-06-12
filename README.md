jcompass (jcompass.jar)
========

Java JRuby with Sass Compass in a single jar

Download the latest copy of JRuby  (At the time of this posting it's version 1.7.4)
(http://www.jruby.org/download Find the "Complete Jar", second link from the bottom in the top group of links for the latest version)


The rest is command line:

# Make a copy of jruby-complete-1.7.4.jar for the new singleton combined jar file
cp jruby-complete-1.7.4.jar jruby-complete.jar

# Now install the gems locally
java -jar jruby-complete.jar -S gem install -i ./compass-gems shared --no-rdoc --no-ri
java -jar jruby-complete.jar -S gem install -i ./compass-gems sass --pre --no-rdoc --no-ri
java -jar jruby-complete.jar -S gem install -i ./compass-gems compass --pre --no-rdoc --no-ri

# Now rename the jruby complete jar file to the name for the new compass jar
mv jruby-complete.jar jcompass.jar

# Now compile together
jar uf jcompass.jar -C compass-gems .

# ALL DONE! Now test it out:
java -jar jcompass.jar -S compass compile --help
java -jar jcompass.jar -S compass compile --sass-dir /relative/or/full/path/to/source/scss/files/ --css-dir /relative/or/full/path/to/destination/css/files/ --force

========

Copyright (c) 2013, GBUILT
This software and instructions are free to use, modify, and distribute.
Restricted by nothing other than any restictions from JRuby http://www.jruby.org
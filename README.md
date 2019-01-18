# Instructions


## Examples

+ rrrun -tool=FT2 test.Test

+ ./TEST -tool=FT2 -array=FINE -field=FINE -noTidGC -availableProcessors=4 -benchmark=1 -warmup=0 RRBench

FIXME: The following are not working.

+ Harness is not found.
rrrun -classpath=/home/swarnendu/iitk-workspace/roadrunner/benchmarks/dacapo-9.12-bach.jar -tool=FT2 -noTidGC -noxml Harness -t 4 -s small avrora

+
To execute a benchmark with java directly:
 - $ /usr/lib/jvm/java-1.8.0/bin/java -javaagent:<Vindicator directory>/build/jar/rragent.jar -Xmx20g -Xbootclasspath/p:<Vindicator directory>/classes:<Vindicator directory>/jars/java-cup-11a.jar: rr.RRMain -classpath=<Vindicator directory>/benchmarks/<provided benchmark>/original.jar -maxTid=14 -array=FINE -field=FINE -noTidGC -availableProcessors=8 -tool=WDC -benchmark=1 -warmup=0 RRBench

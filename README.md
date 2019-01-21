# Instructions

This document augments instructions that are already provided by the unmodified RoadRunner framework. Check `INSTALL.txt` and `rrrun -help`.

## Browsing the Source

Read the comments at the beginning of the RRMain class.

## Examples

Note that RoadRunner current supports only till Java 1.8.

+ rrrun -tool=FT2 test.Test -benchmark=10 -warmup=3

+ ./TEST -tool=FT2 -array=FINE -field=FINE -noTidGC -availableProcessors=4 -benchmark=1 -warmup=0 RRBench

+ rrrun -classpath=original.jar -tool=FT2 -noTidGC -noxml Main -t 4 -s small (for avrora)

## Benchmarks

The following benchmarks should work with RoadRunner.

    + Working
        + avrora
        + batik
        + fop
        + h2
        + jython
        + luindex
        + lusearch
        + pmd
        + sunflow
        + tomcat

I haven't been able to get the following to work, they seem to fail in vanilla RoadRunner.

    + Not working
        + crypt
        + lufact
        + moldyn
        + montecarlo
        + raytracer
        + series
        + sor
        + sparsematmult
        + xalan

## Questions


FIXME: The following are not working.

+ Harness is not found

    rrrun -classpath=/home/swarnendu/iitk-workspace/roadrunner/benchmarks/dacapo-9.12-bach.jar -tool=FT2 -noTidGC -noxml Harness -t 4 -s small avrora

+ To execute a benchmark with java directly:

    java -javaagent:/home/swarnendu/iitk-workspace/roadrunner/build/jar/rragent.jar -Xmx20g -Xbootclasspath/a:/home/swarnendu/iitk-workspace/roadrunner/classes:/home/swarnendu/iitk-workspace/roadrunner/jars/java-cup-11a.jar: rr.RRMain -classpath=/home/swarnendu/iitk-workspace/roadrunner/benchmarks/pmd/original.jar -maxTid=14 -array=FINE -field=FINE -noTidGC -availableProcessors=8 -tool=FT2 -benchmark=1 -warmup=0 RRBench

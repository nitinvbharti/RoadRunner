# Instructions

SB: NOTE: This document *augments* instructions that are already provided by the unmodified RoadRunner framework. Check `README-RoadRunner.txt`, `INSTALL.txt`, and run `rrrun -help`.

## Browsing the Source

Read the comments at the beginning of the `RRMain` class.

+ Important classes
    +

## Invocation Examples

Note that RoadRunner current supports only till Java 1.8.

+ Build: `ant`
+ Clean: `ant clean`
+ Export RoadRunner binary paths: `source msetup`

You might want to change the value of `-Xmx` and `availbleProcessors` depending on your system configuration.

+ `avrora`: `cd benchmarks/avrora`

    + `./TEST -tool=FT2 -array=FINE -field=FINE -noTidGC -availableProcessors=4`

    + `rrrun -tool=FT2 -benchmark=10 -warmup=3`

    + `./TEST -tool=FT2 -array=FINE -field=FINE -noTidGC -availableProcessors=4 -benchmark=1 -warmup=0 RRBench`

    + `rrrun -classpath=original.jar -tool=FT2 -array=FINE -field=FINE -noTidGC -noxml -availableProcessors=4 -benchmark=1 -warmup=0 Main -t 4 -s small`

+ To execute `avrora` with `java`: `cd benchmarks/avrora`

    `java -javaagent:/home/swarnendu/iitk-workspace/roadrunner/build/jar/rragent.jar -Xmx10g -Xbootclasspath/a:/home/swarnendu/iitk-workspace/roadrunner/classes:/home/swarnendu/iitk-workspace/roadrunner/jars/java-cup-11a.jar: rr.RRMain -classpath=/home/swarnendu/iitk-workspace/roadrunner/benchmarks/avrora/original.jar -maxTid=14 -array=FINE -field=FINE -noTidGC -availableProcessors=4 -tool=FT2 -benchmark=1 -warmup=0 RRBench`

+ To execute `xalan` with `java`: `cd benchmarks/xalan`

    `/usr/lib/jvm/java-8-openjdk-amd64/bin/java -javaagent:/home/swarnendu/plass-workspace/vindicator/build/jar/rragent.jar -Xmx10g -Xbootclasspath/p:/home/swarnendu/plass-workspace/vindicator/classes:/home/swarnendu/plass-workspace/vindicator/jars/java-cup-11a.jar: rr.RRMain -classpath=/home/swarnendu/plass-workspace/vindicator/benchmarks/xalan/original.jar -maxTid=14 -array=FINE -field=FINE -noTidGC -availableProcessors=4 -tool=FT2 -benchmark=1 -warmup=0 RRBench`

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
        + xalan

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

## Questions

## Notes

DaCapo Harness is not supported out of the box by RoadRunner, hence we cannot run the following.

    `rrrun -classpath=/home/swarnendu/iitk-workspace/roadrunner/benchmarks/dacapo-9.12-bach.jar -tool=FT2 -noTidGC -noxml Harness -t 4 -s small avrora`

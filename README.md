WebGL Performance Benchmark
==========

To run the benchmarks, either download it onto your computer and run it with a WebGL capable browser, or simply visit: http://luic.github.io/WebGL-Performance-Benchmark/

The goal of the project was to create a web-based open source graphics benchmark with HTML5 and WebGL using a testing metric other than frame rate. The project client was Remi Arnaud from AMD, and he proposed this project in order to experiment with a new format of GPU testing that the functionality of WebGL now gives us access to. The research and coding was done by Byron Kropf and Charles Lui, with guidance and supervision by Remi Arnaud.

This is a significant project because 3D graphics are becoming more and more prevalent, and our project provides a way to accurately measure the graphics performance on a device. The main benchmark in the project does not use the typical measurement, frames per second, to measure the graphical performance of the computer. Instead, it measures the amount of work that a device can do in the time period of a single frame. We cannot use frames per second as a measurement of graphics performance because it can be inaccurate in the context of a web browser; this is where the project comes into play.

We accomplished our goal of prototyping a new way of benchmarking graphics performance in a web browser. In addition, when we started getting data out of our benchmark, the results supported the theoretical results that we were looking for, which was quite encouraging.

Our benchmark works by testing the amount of work that your GPU can process into a single frame rather than the typical benchmark metric of how many frames can be processed in a second. This is achieved by drawing an increasing number of objects in each frame, and looking for where the number of objects being used forces the GPU to break the job into multiple frames. In order to reduce error caused by the complexity of the objects used, we made the objects as simple as possible, all of the objects are screen filling rectangles of a flat color.

The test runs for a number of frames that changes depending on the capability of the system being tested. By default, the test will currently run for 100 frames, if the test finds that it didn't stress the card enough, then the benchmark will be extended until it does. Stressing the card is defined by, when the work takes more than 4 frames of time to render.

When the test is completed we use the D3.js library to display a graph of the data collected. The general graph trend will have a stair step pattern to it with each stair step indicating another frame that was needed in order to process the current number of objects. Having more objects that can be added before each stair step in the graph indicates a better performing graphics card.

For the most consistent benchmark results, don't run other intensive applications while attempting to benchmark your system. Also, switching web browser tabs while running the benchmark may affect your results due to the web browser changing the priority of the benchmark process. 

Authors: Charles Lui, Byron Kropf, Rémi Arnaud

# REM-SPMD
Replica Exchange Using Swarm Particle-like Molecular Dynamics 

This is a C++ computer program for performing Replica Exchange Standard and/or Swarm Particle-like Molecular Dynamics Simulations of
(bio)molecular systems using Coarse-graining models for proteins. The coarse-graining model includes these terms:
1 - Electrostatic interactions by assigning a single charge to each residue;
2 - van der Waals interactions;
3 - bond-stretching term;
4 - angle bending term;
5 - torsion angle term

Some features of the dynamics include:
    Massive Nose-Hoover chain of thermostats approach;
    Dynamics are augmented using Swarm Particle-like Molecular dynamics technique;
    Time-reversible numerical integrators are used solving augmented system of differential equations.
    
Program has been tested to run without errors in Mac, Windows (MinGW compilers) and Linux operating systems.
To run the program simply type from 'exec' folder:

dist\Debug\Win\run1.exe -nreplicas 10 -nthermos 10 -nparticles 4 -niter 10000 -nskip 100 -nstart 5000 -nswaps 10 -tempi 20 -tempf 420 -qbias 1
    
where:

nreplicas  -  Is the number of replicas;
nthermo    - Is the number of thermostats coupled to replicas;
nparticles - Is number of coarse-grained particles representing the system;
niter      - Is the number of Molecular Dynamics steps;
nskip      - Is the number of frames to skip between output configurations;
nstart     - Is the length of equlibration of system;
nswaps     - Is the number of steps between the swaps of replica exchange dynamics;
tempi      - Is the temperature of the first thermostat;
tempf      - Is the temperature of the last thermostat;
qbias      - is a flag: if qbias = 0 standard REM:MD is run; if qbias=1, then REM:SPMD is run.

Temperatures between tempi and tempf are chosen according to geometrical distribution.

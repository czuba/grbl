# ViewDist Grbl Settings

### Rig1 NHB

TBC, steady-state, 2019-01-23

Open connection in Matlab with:
```
G = grbl.open
```

*buildInfo*
```
msg = grbl.write(G, G.cmd.buildInfo)
msg =
    '[VER:1.1e.20170114:NHBRIG1_VIEWDIST]
     [OPT:VZ]
     ok
     '
```

## Grbl settings


*startBlocks*
```
msg = grbl.write(G, G.cmd.startBlocks)
msg =
    '$N0=G21G90G93
     $N1=
     ok
     '
```


*G.settings*

- These settings were tuned for the ViewDist rig in NHB
- Use as a guideline only after understanding how each one works (see grbl wiki on github)


```
G.settings
ans = 
  struct with fields:

           stepPulse: [0 5]
       stepIdleDelay: [1 25]
          stepInvert: [2 0]
           dirInvert: [3 0]
    stepEnableInvert: [4 0]
        limPinInvert: [5 0]
      probePinInvert: [6 0]
          statOutput: [10 1]
       jnctDeviation: [11 0.01]
              arcTol: [12 0.002]
        reportInches: [13 0]
            softLims: [20 1]
            hardLims: [21 1]
           homingCyc: [22 1]
     homingDirInvert: [23 1]
          homingFeed: [24 25]
          homingSeek: [25 150]
        homeDebounce: [26 20]
         homePullOff: [27 3]
          spindleMax: [30 12000]
          spindleMin: [31 0]
           laserMode: [32 0]
             xStepSz: [100 175]
             yStepSz: [101 200]
             zStepSz: [102 200]
            xMaxRate: [110 600]
            yMaxRate: [111 1500]
            zMaxRate: [112 1500]
              xAccel: [120 2.5]
              yAccel: [121 30]
              zAccel: [122 30]
          xMaxTravel: [130 92.5]
          yMaxTravel: [131 1000]
          zMaxTravel: [132 500]
```




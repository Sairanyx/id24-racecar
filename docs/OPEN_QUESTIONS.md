# Open questions

Shared list of things we don't know yet or have not agreed on. Tick items off as they are
answered, and record the answer here rather than only in a meeting.

## For Amin / the coach

- [ ] **Can we attach a marker (e.g. ArUco) to the car?**
      This is kinda important. If yes, we can generate training
      labels automatically and skip most manual annotation.
- [ ] Does the trained detection model need to be the centrepiece of the
      project, or is a working system with good geometry acceptable?
- [ ] Is AGPL licensing a problem? It decides whether we can use
      Ultralytics YOLO or should prefer RF-DETR / RTMDet.
- [ ] Car telemetry - what does it send, over what interface, at what rate?

## Camera hardware

- [ ] Resolution
- [ ] Frame rate
- [ ] USB or IP (RTSP)? Power over Ethernet?
- [ ] Lens type - wide angle or fisheye?
- [ ] How much freedom do we have over mounting angle?
- [ ] Can we control exposure and white balance manually?
      Automatic exposure changing mid-session causes avoidable problems.

## Camera placement

Two requirements that cannot be fixed in software later:

- [ ] **Overlapping coverage** - the only way to measure our own accuracy
- [ ] **As close to overhead as the beams allow** - oblique angles amplify
      the height projection error

## Track

- [ ] Final track layout and dimensions
- [ ] Remeasure the car properly - length, body width, wheel-to-wheel
      width, and height off the floor. Rough numbers are in
      `configs/penalties.yaml` and roughly match the Tamiya spec, but the
      wheel width decides when a boundary penalty triggers so it should
      be measured accurately. Wheel spacing is adjustable, so recheck if
      anyone changes the setup.
- [ ] Where is the coordinate origin? Which direction is +x?

## Team decisions

- [ ] Repository under a personal account or a shared organisation?
- [ ] Storage location on the lab PC, and a backup location
- [ ] Who owns which component
- [ ] GitHub usernames for all five people

## More to Decide

- Offline processing, not real time?
- Ubuntu 26.04 LTS as the development environment under WSL2?
- GitHub, `main` protected, work via pull requests?


## Decided

- Raw data never goes in git
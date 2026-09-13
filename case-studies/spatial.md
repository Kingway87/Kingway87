# Othersmind Spatial

**An interface you can approach with your hands as well as language.**

Spatial experiment · simulated environment · source not published on GitHub · September 2026 snapshot

## The question

What changes when an AI interface can act on a shared spatial scene rather than only respond in text?

## What exists

The prototype combines MediaPipe hand tracking, smoothing and gesture logic, a React Three Fiber / Three.js scene, and a bounded set of scene tools. A model-facing route can interpret a request and use those tools. Gesture state and scene commands have deterministic tests.

```text
camera → hand landmarks → filtering / gesture state ─┐
                                                     ↓
language → bounded tool loop → validated command → scene
                                                     ↓
                                            visible state change
```

The scene includes approximate procedural geometry and simulated telemetry. It is not connected building infrastructure or a verified operational digital twin.

## The engineering choices

- Separate noisy hand input from stable interaction state.
- Give the model named scene operations rather than unrestricted execution.
- Stage validated scene actions and reject delayed model results when direct input has changed the scene.
- Make an action's consequence visible in the same environment.
- Test geometry, camera, and interaction state separately from model behavior.

## What was checked

Seventy-three tests across eight test files passed in an isolated copy. Coverage included gesture behavior, scene/camera state, and mocked agent routes. That is not a fresh end-to-end webcam study or a live-model usability result.

## What is unfinished

Camera behavior varies with lighting, occlusion, hardware, and hand position. The experience needs a fresh reproducible interaction demo and repeated user testing, including its existing mouse and alternate gesture controls. The quality of model-driven interaction remains a separate evaluation question.

## The next useful experiment

Record the same task with mouse controls, hand gestures, and language: select an object, move the camera, inspect a property, and undo a mistake. Compare failure recovery, not just how futuristic the first interaction looks.

[Back to the lab](../README.md)

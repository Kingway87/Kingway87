# Puzzle Pointer

**Finding a physical puzzle piece's possible place with computer vision.**

Computer-vision prototype · local source · web and native iOS interfaces

## The problem

A suggested placement should explain when it is uncertain. A convincing camera overlay is not enough if the matcher quietly produces the wrong result.

## What exists

The project includes a FastAPI/OpenCV matching backend, a web interface, native SwiftUI client code, matcher tests, and benchmark material. The classical matching path combines segmentation, rotation and scale search, color/texture/edge scores, ORB feature refinement, and candidate-region filtering. Its confidence values are heuristics, not statistical probabilities; no LLM is required.

The iOS application defaults to a synthetic mock service. A remote HTTPS client exists, but that does not prove a completed live mobile-to-backend experience.

## Why it is worth showing

It crosses the physical/digital boundary and makes confidence visible as a product problem. It also broadens the profile beyond chat wrappers: useful AI-era software can include deterministic computer vision.

## Current boundary

The matcher tests were inspected but were not run during this review: the available Python environments lacked the required OpenCV, FastAPI, and pytest dependencies. The project still needs a fresh end-to-end device demonstration. No real-world matching-accuracy figure is claimed here. Benchmark fixtures and selected examples are not proof of accuracy across arbitrary puzzles, lighting, or cameras.

## The next useful experiment

Create a held-out set of photos with varying angles and lighting. Measure whether the correct neighborhood appears among the candidates, uncertainty, and confident errors. Show one failure alongside the successful demonstration.

[Back to the lab](../README.md)

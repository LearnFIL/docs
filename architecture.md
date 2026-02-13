# Architecture Overview

## High level view

LearnFIL is designed as a local-first learning application that runs entirely in the browser, with optional decentralized extensions.

There is no required backend server.

Core layers:
- Browser application
- Local state management
- Optional decentralized persistence
- Optional peer to peer networking
- External interfaces via bots

## Current architecture

### Browser application
The main LearnFIL app is a single page application that:
- Displays lessons and modules
- Executes learner code locally
- Validates results in the browser
- Tracks progress locally

All logic runs client side.

### Validation engine
Lessons include validation tests that:
- Execute against learner code
- Return pass or fail
- Gate lesson completion

Validation is deterministic and local.

### No centralized backend
There is currently:
- No API server
- No centralized database
- No authentication requirement

This is an intentional design choice.

## Evolving architecture

LearnFIL is being extended with decentralized primitives instead of centralized services.

These extensions include:
- Filecoin onchain cloud for verifiable checkpoints
- libp2p for peer discovery and event propagation
- Telegram and Discord bots as external interfaces

These additions do not replace the core app. They augment it.

## Design principles

- Local first
- Offline capable
- No mandatory accounts
- Verifiable over time
- Network native instead of server centric
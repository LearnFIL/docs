# Bots, Agents, and External Interfaces

## Overview

LearnFIL integrates Telegram and Discord bots as external interfaces to the learning network.

Bots are not authoritative systems.
They are interfaces and coordinators.

## What bots do

Bots can:
- Share lesson and module information
- Announce completions and achievements
- Surface learning checkpoints
- React to network events
- Guide learners to next steps

Bots do not:
- Execute lesson code
- Validate solutions
- Store authoritative progress
- Replace the web app

## Current bot work

Work in progress includes:
- Telegram bot scaffolding
- Discord bot scaffolding
- Message handlers for lesson discovery
- Event handling for learning milestones

Bots currently rely on:
- Local state references
- Future libp2p events
- Filecoin checkpoint CIDs

## libp2p integration

libp2p is used as the networking layer to:
- Discover peers
- Broadcast learning events
- Synchronize metadata
- Coordinate bots and agents

There is no central coordinator.

## Agent model

Bots are treated as agents:
- They observe the network
- They react to events
- They provide guidance
- They remain stateless

This allows multiple communities to interoperate without shared infrastructure.

## Current status
- Bot foundations are implemented
- libp2p event flow is in progress
- Full peer discovery and sync is upcoming
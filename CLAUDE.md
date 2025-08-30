# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a custom growth blueprint system for B2B marketing services. It's a YAML-based configuration system that manages:

- **Marketing capabilities catalog** with effort points, prerequisites, and deliverables
- **Client intake and discovery sessions** with structured business requirements  
- **Weekly reporting schema** for tracking metrics and progress updates
- **Pricing tiers** with point-based billing system

## Architecture

The repository follows a structured YAML-based approach:

### Core Components

- **`/catalog/`** - Marketing service definitions
  - `capabilities.yaml` - Available marketing services (ABM, content strategy, automation, etc.) with effort points and prerequisites
  - `pricing.yaml` - Service pricing tiers, billing structure, and add-on options

- **`/intake/`** - Client onboarding data
  - Discovery session templates with company info, current state, goals, and constraints

- **`/clients/{client_id}/weeks/`** - Client progress tracking  
  - Weekly update files following the schema structure with metrics and changelog entries

- **`/automation/schemas/`** - Data structure definitions
  - `weekly_update_schema.yaml` - Defines required fields and changelog types for client reporting

### Key Concepts

- **Effort Points System**: Each capability has effort points that map to pricing tiers
- **Prerequisites**: Some capabilities require others to be completed first (e.g., marketing automation requires content strategy)
- **Changelog Types**: Standardized categories for weekly updates (action, insight, ask, risk)
- **Client Segmentation**: Primary/secondary target segments with specific pain points

## Data Structure Conventions

- Client IDs use snake_case format (e.g., "techflow_solutions")  
- Week ending dates follow YYYY-MM-DD format (always Friday)
- Monetary values are in USD without currency symbols
- Changelog entries must include type, title, and description fields
- Impact levels are categorized as "low", "medium", or "high"

## No Build/Test Commands

This is a pure configuration/data repository with no build process, dependencies, or automated testing. All files are static YAML configurations.
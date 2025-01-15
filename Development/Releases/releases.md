<!-- u250114 -->

> Last updated: January 14, 2025

<div align="center">

![logo](../../.github/Images/Logos/TingenDevelopmentDocumentation-232x308.png)

 <h1>Releases</h1>

</div>

There are five types of Tingen releases:

- [Development](#development)
- [Testing](#testing)
- [Release](#release)
- [Stable](#stable)
- [Community](#community)

# Development

TBD

# Testing

TBD

# Release

```mermaid
flowchart LR
  %% Components
  DailyDevelopment@{shape: rounded, label: "Daily development"}
  ReleaseCandidate@{shape: stadium, label: "Release candidate"}
  Testing@{shape: rounded, label: "Testing"}
  %% Layout
  DailyDevelopment -- Successful testing --> ReleaseCandidate
  DailyDevelopment -- Fixes/Updates --> ReleaseCandidate
  %% Styles
  style DailyDevelopment color:#000,fill:#ff9800,stroke:#42a5f5,stroke-width:3px
  style ReleaseCandidate color:#000,fill:#ff9800,stroke:#26c6da,stroke-width:3px
  style Testing color:#000,fill:#ff9800,stroke:#42a5f5,stroke-width:3px
```

# Stable

TBD

# Community

- December 20: Abatab WinterYY
- March 20: Abatab SpringYY
- June 20: Abatab SummerYY
- September 20: Abatab AutumnYY

For example: `Abatab Autumn23`
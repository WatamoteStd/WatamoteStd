# Immortals and Heroes (IaH) — Production Repository

Production-ready, high-performance distributed architecture for a Dark Fantasy MMORPG/MOBA with a player-driven economy. 

---

## 🏗️ System Architecture

The ecosystem uses a split three-tier architecture designed to maximize throughput, eliminate allocation overhead, and ensure strict state validation.

### 1. Master Server (Control Plane)
*   **Tech Stack:** ASP.NET Core (.NET 10), Entity Framework Core, PostgreSQL.
*   **Responsibility:** Handles heavy, non-realtime operations including user authentication, secure JWT generation, persistent character storage, and global market state.

### 2. Realtime Game Server (Data Plane)
*   **Tech Stack:** Custom lightweight C# UDP Server built on raw sockets.
*   **Responsibility:** High-tickrate simulation handling spatial positioning, combat hitreg, and rapid state synchronization. Uses a custom binary protocol optimized to run with zero heap allocations.

### 3. Client Engine
*   **Tech Stack:** Godot Engine (C#).
*   **Responsibility:** Dual-channel networking. Uses an `HttpClient` wrapper for HTTPS communication with the Master Server and a dedicated high-frequency socket loop using `ReadOnlySpan<byte>` for real-time UDP replication.

---

## 🛠️ Core Stack & Metrics

<p align="left">
  <img src="https://img.shields.io/badge/c%23-%23239120.svg?style=for-the-badge&logo=c-sharp&logoColor=white" alt="C#">
  <img src="https://img.shields.io/badge/.NET10-%25512BD4.svg?style=for-the-badge&logo=.net&logoColor=white" alt=".NET">
  <img src="https://img.shields.io/badge/Godot-%23478cbf.svg?style=for-the-badge&logo=godot-engine&logoColor=white" alt="Godot">
  <img src="https://img.shields.io/badge/PostgreSQL-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL">
</p>

<p align="left">
  <img src="https://github-readme-stats.vercel.app/api?username=WatamoteStd&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true" alt="Metrics" height="190">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=WatamoteStd&layout=compact&theme=tokyonight&hide=html,css" alt="Languages" height="190">
</p>

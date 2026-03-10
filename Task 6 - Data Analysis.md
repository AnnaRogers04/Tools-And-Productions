# Steam Hardware & Software Survey – Analysis Report

## Dataset Description

This dataset originates from the [Steam Hardware & Software Survey](https://store.steampowered.com/hwsurvey), a voluntary, anonymous monthly survey that collects hardware and software telemetry from Steam's user base. The dataset contains **operating-system usage data** across two survey periods (February 2022 and February 2026) with the following fields:

| Column | Description |
|---|---|
| `Month` | Survey period (YYYY-MM) |
| `OS_Name` | Specific operating-system version |
| `Share_Percent` | Percentage of Steam users running that OS |
| `Change_Percent` | Month-over-month delta in share |
| `Category` | OS family – **Windows**, **OSX**, or **Linux** |

Data cleaning applied: corrupted `Category` values were corrected by inferring the OS family from the `OS_Name` field; numeric columns were coerced; empty and duplicate rows were dropped.

---

## 1. OS Family Market Share

<img width="1600" height="1000" alt="image" src="https://github.com/user-attachments/assets/87e3a0d0-7364-4c80-9603-758a9468a04f" />

**Windows** commands an overwhelming **96.61 %** of the Steam ecosystem. **Linux** follows at **2.23 %**, slightly ahead of **macOS** at **1.16 %**. Together, non-Windows platforms account for roughly **3.4 %** of all Steam users — a small but non-trivial audience for cross-platform development.

---

## 2. Linux Distribution Breakdown

![Linux Distribution Breakdown](linux_distribution_share.png)

Among Linux users, **Arch Linux** leads at **0.19 %** share, followed closely by **Ubuntu 20.04 LTS** (0.16 %) and **Linux Mint 22.3** (0.14 %). The distribution is heavily fragmented — no single distro exceeds 0.2 % of all Steam users. Notably:

- **Rolling-release distros** (Arch, Manjaro) together represent a significant portion, likely reflecting the gaming-oriented audience that favours fresh drivers and kernel updates.
- **Ubuntu LTS variants** remain popular baselines, consistent with their status as the primary target for Proton and Steam's official support.
- **Linux Mint** appears in multiple versions, indicating a loyal user base that upgrades incrementally.

---

## 3. Linux Share Changes (Month-over-Month)

![Linux Share Changes](linux_share_change.png)

The month-over-month change chart reveals a mixed picture:

| Trend | Distributions |
|---|---|
| **Growing** | Arch Linux (+0.19 %), Linux Mint 22.3 (+0.06 %), Ubuntu 20.04 LTS (+0.03 %), Manjaro (+0.01 %) |
| **Declining** | Linux (All) (−1.15 %), Linux Mint 22.2 (−0.17 %), Ubuntu 24.04 LTS (−0.07 %), Ubuntu Core 24 (−0.05 %), Ubuntu 21.10 (−0.01 %) |

The large aggregate decline (−1.15 % for "Linux (All)") suggests that while certain individual distributions are growing, the overall Linux share has dipped — potentially due to seasonal effects or users migrating back to Windows for specific titles.

---

## 4. Windows Version Comparison

![Windows Version Comparison](windows_versions_share.png)

**Windows 11 64-bit** has surpassed Windows 10 to become the dominant version at **56.28 %**, compared to **40.25 %** for **Windows 10 64-bit**. Legacy versions (Windows 7, 8.1, 32-bit editions) collectively account for less than 1 %. This indicates the Steam user base is actively migrating to the latest Windows release, which has implications for DirectX 12 and HDR adoption in game development.

---

## 5. Overall Top OS Versions

![Top OS Versions](top_os_versions.png)

The top-15 leaderboard is dominated by the two major Windows releases. After a significant drop-off from Windows 10 (40.25 %), the remaining entries are below 1 % each. macOS versions cluster between 0.14 – 0.46 %, while Linux distributions appear in the lower tier at 0.14 – 0.19 %. This visualization underscores the extreme concentration of the Steam ecosystem on Windows.

---

## 6. Historical Comparison: OS Family Share (2022 vs 2026)

![OS Family Comparison 2022 vs 2026](os_family_comparison_2022_vs_2026.png)

Side-by-side comparison of OS family share across the 4-year gap. Windows remained essentially flat (96.23 % → 96.61 %, +0.38 pp). The more dramatic shifts occurred in the minority platforms: **Linux quadrupled** from 0.56 % to 2.23 %, while **macOS nearly halved** from 2.18 % to 1.16 %. Linux has overtaken macOS as the second-largest OS family on Steam.

---

## 7. OS Family Share Change (2022 → 2026)

![OS Family Change Delta](os_family_change_2022_to_2026.png)

The delta chart highlights the magnitude of change:

| OS Family | 2022 | 2026 | Δ |
|---|---|---|---|
| **Windows** | 96.23 % | 96.61 % | **+0.38 pp** |
| **macOS** | 2.18 % | 1.16 % | **−1.02 pp** |
| **Linux** | 0.56 % | 2.23 % | **+1.67 pp** |

Linux's +1.67 percentage-point gain is the largest absolute movement among the three families, representing a **~298 % relative increase** in share.

---

## 8. Windows Versions: 2022 vs 2026

![Windows Versions 2022 vs 2026](windows_versions_2022_vs_2026.png)

The Windows landscape shifted dramatically. In 2022, **Windows 10 dominated** at 73.5 % and Windows 11 was emerging at 18.9 %. By 2026, the positions have effectively **reversed**: Windows 11 now leads at **56.3 %** while Windows 10 has fallen to **40.2 %**. Legacy versions (Windows 7, 8.1) have essentially disappeared from the platform.

---

## 9. Linux Distributions: 2022 vs 2026

![Linux Distributions 2022 vs 2026](linux_distributions_2022_vs_2026.png)

Several distributions appear exclusively in the 2026 data (Linux Mint 22.3, Ubuntu Core 24, Ubuntu 24.04 LTS, Linux Mint 22.2), reflecting the natural lifecycle of distro releases. Arch Linux grew from 0.14 % to 0.19 % — a **36 % relative increase**. Manjaro remained stable. The emergence of new Ubuntu and Mint versions in 2026 confirms active distro-hopping and upgrade behaviour within the Linux gaming community.

---

## 10. macOS Versions: 2022 vs 2026

![macOS Versions 2022 vs 2026](macos_versions_2022_vs_2026.png)

Most macOS 12.x versions from 2022 have largely disappeared by 2026, replaced by newer macOS 26.x and 15.x entries. The overall macOS share decline (−1.02 pp) suggests that macOS gamers may be shifting to other platforms, or that Apple's move to ARM (M-series chips) created a temporary compatibility gap with Steam games.

---

## 11. Linux & macOS Share – Zoomed Comparison

![Linux vs macOS Zoomed](linux_macos_share_2022_vs_2026.png)

This zoomed view isolates the non-Windows platforms. The crossover is striking: in 2022, macOS (2.18 %) was **nearly 4× larger** than Linux (0.56 %). By 2026, **Linux (2.23 %) has overtaken macOS (1.16 %)**, reversing the historical relationship. This is likely driven by the Steam Deck's Arch-based SteamOS and Valve's continued investment in Proton.

---

## Linux Ecosystem Insights

### Current Position

Linux holds a **2.23 %** share of the Steam platform (up from 0.56 % in 2022). While small in absolute terms, this represents **millions of active users** given Steam's total user base (estimated at 130+ million monthly active users), translating to roughly **2.9 million Linux gamers** — a **4× increase** over 4 years.

### Growth vs. Decline Trends

**Long-term (2022 → 2026):** Linux share grew by +1.67 percentage points — the largest absolute gain of any OS family. This growth is structurally driven by the Steam Deck and Proton maturation.

**Short-term (month-over-month):** The latest month-over-month data shows a −1.15 % aggregate dip, but individual distributions like Arch Linux and Linux Mint 22.3 are growing. This paradox is explained by:

1. **Version migration** — users upgrading between distro versions (e.g., Mint 22.2 → 22.3) show up as decline on the old version and growth on the new.
2. **Seasonal variation** — gaming activity on Linux can fluctuate around major game releases that may or may not have Day-1 Proton support.

### Implications for Proton Compatibility and Linux Gaming

| Factor | Assessment |
|---|---|
| **User base viability** | 2–3 % is sufficient to justify continued Proton investment. The 4× growth from 2022 validates Valve's strategy. |
| **Linux overtaking macOS** | Linux has surpassed macOS on Steam — a milestone that strengthens the case for Linux-first (rather than Mac-first) cross-platform support. |
| **Distribution fragmentation** | 9 unique distributions in the dataset; Proton and Steam Runtime must target multiple package managers and library versions. Ubuntu LTS remains the safest baseline. |
| **Rolling-release popularity** | Arch and Manjaro's prominence means Proton must keep pace with bleeding-edge `mesa`, `glibc`, and kernel releases. |
| **Trend direction** | Long-term trend is strongly positive despite short-term fluctuations. Continued Steam Deck sales should sustain growth. |

### Recommendations

1. **Continue targeting Ubuntu LTS** as the primary "reference" platform for Proton testing.
2. **Maintain Arch/Manjaro CI pipelines** — these rolling-release users are disproportionately likely to file bug reports and contribute to the ecosystem.
3. **Prioritize Linux over macOS** for cross-platform support investments, given Linux's overtake and stronger growth trajectory.
4. **Leverage Steam Deck momentum** — the Deck's default SteamOS (Arch-based) is a natural funnel for converting users into the Linux gaming ecosystem.
5. **Monitor the aggregate trend** over the next 2–3 survey cycles to confirm the long-term trajectory remains positive.

---

*Report generated from Steam Hardware & Software Survey data. Source: [store.steampowered.com/hwsurvey](https://store.steampowered.com/hwsurvey)*

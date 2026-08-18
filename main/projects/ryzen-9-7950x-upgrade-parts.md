---
created: 2026-08-17
class:
  - project
description: core components list for full platform upgrade from Ryzen 3 3200G (AM4) to Ryzen 9 7950X (AM5)
mod.: 2026-08-17
aliases:
  - 7950x build
  - pc upgrade
tags:
  - hardware/pc-build
  - hardware/amd
---

## current system

| component | model |
|-----------|-------|
| cpu | AMD Ryzen 3 3200G (4c/4t, Zen+) |
| gpu | Integrated Radeon Vega 8 |
| ram | ~13.6GB DDR4 (mixed sticks, likely single-channel) |
| boot drive | 250GB SATA SSD (WDC WDS250G2B0B) |
| data drive | 1TB HDD (WDC WD10EZEX, 7200RPM) |
| os | Arch Linux (kernel 6.19) |

## upgrade parts list

| #   | component   | model                                                    | est. price |
| --- | ----------- | -------------------------------------------------------- | ---------- |
| 1   | cpu         | AMD Ryzen 9 7950X (16c/32t, 5.7GHz boost, Zen 4)         | ~$450–500  |
| 2   | motherboard | MSI MAG X870 Tomahawk WiFi (AM5, ATX)                    | ~$280      |
| 3   | ram         | G.Skill Trident Z5 Neo 32GB (2x16GB) DDR5-6000 CL30 EXPO | ~$110      |
| 4   | boot ssd    | WD Black SN7100 2TB NVMe (PCIe 4.0)                      | ~$140      |
| 5   | cpu cooler  | Thermalright Peerless Assassin 120 SE                    | ~$35       |
| 6   | psu         | Corsair RM850e (80+ Gold, fully modular, ATX 3.0)        | ~$100      |

**total: ~$1,115–1,165**

## component notes

### cpu — ryzen 9 7950X
- 16 cores / 32 threads, 5.7GHz boost clock
- single-thread performance is faster than threadripper 7960X (+3-5%)
- 170W TDP — designed to boost to 95°C by design, not a cooling failure
- drop-in upgrade from any AM4 chip (requires new AM5 board)

### motherboard — msi mag x870 tomahawk
- 14+2+1 VRM power stages — handles 170W without throttling
- wifi 7 (mediatech mt7925, works on arch out of the box)
- usb4 ports, 5G LAN
- 2x PCIe 5.0 M.2 slots, 2x PCIe 4.0 M.2 slots
- BIOS ships ryzen 7000-ready out of the box
- x870 over b650 for: usb4, wifi 7, more Gen5 M.2 slots

### ram — g.skill trident z5 neo 32GB DDR5-6000 CL30
- 6000MHz CL30 is the sweet spot for zen 4 — maintains 1:1 FCLK ratio
- going above 6000MHz forces 2:1 mode, which increases latency
- AMD EXPO for one-click overclocking in BIOS
- 32GB is plenty for gaming + dev work
- 64GB (2x32GB, ~$180) only if doing heavy VMs or 8K video editing

### boot ssd — wd black sn7100 2TB
- PCIe 4.0, 7,250 / 6,900 MB/s sequential read/write
- gen4 is the value play — gen5 (WD SN8100 at 14,900 MB/s) costs 2x more with indistinguishable daily-use difference
- single-sided, runs cool, 5-year warranty / 600TBW per TB
- 2TB gives room for root partition + apps + games

### cpu cooler — thermalright peerless assassin 120 SE
- 6 heatpipes, dual tower, dual 120mm fans
- rivals $140 coolers (Noctua NH-D15 territory) at $35
- keeps 7950X at its designed 95°C thermal target without throttling
- 155mm height — measure future case clearance
- aIO alternative: ARCTIC Liquid Freezer III Pro 360 (~$90) runs 5-10°C cooler but not necessary

### psu — corsair RM850e
- 850W gives headroom for future GPU upgrade (RTX 4070 Super / 4060 Ti)
- 80+ Gold, fully modular
- ATX 3.0 ready — includes 12VHPWR cable for RTX 40-series, no adapter needed
- MSI recommends 750W minimum for 7950X + RTX 4070 class GPU

## keeping from current system

| component | keep? | notes |
|-----------|-------|-------|
| 1TB HDD (WD10EZEX) | yes | mount as secondary storage via SATA on x870 |
| 250GB SSD (WDS250G2B0B) | optional | can keep as scratch disk or sell — too small for modern root |
| case | maybe | only if it fits ATX + 155mm cooler clearance |
| fans | yes | reuse if still functional |

## future GPU upgrade (when ready)

| gpu | est. price | notes |
|-----|------------|-------|
| RTX 4070 Super | ~$550 | pairs perfectly with 7950X for 1440p gaming |
| RTX 4060 Ti | ~$380 | budget option, still a massive leap from Vega 8 |

## linux notes (arch)
- AM5 + Ryzen 7000 works on modern kernels (6.19+, no issues)
- WiFi 7 (MT7925) works out of the box on arch
- all NVMe drives (SN7100, 990 Pro) have excellent linux support
- no proprietary drivers needed for basic functionality

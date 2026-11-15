# Caithness Cetaceans

Marine mammals and cetaceans on the Caithness coast — Thurso, Dunnet,
John o' Groats, Dunnet Head, Duncansby Head, Scrabster, Dunnet Bay,
Sandside Bay and the Pentland Firth. Static GitHub Pages site.

Deploy: `gh.py sync` to a new repo named `ian-cleary/caithness-cetaceans`
(index.html + data.json at the root; the workflow file goes to
`.github/workflows/update-sightings.yml`).

## Live feed

`fetch_sightings.py` queries the public iNaturalist API (no key) for
mammal observations inside the Caithness coast box
(lat 58.30–58.80, lng −4.60–−2.70), keeps the marine species, drops
records whose place text says Orkney, and writes `data.json`
(up to 30 records, most recent first). `update-sightings.yml` runs it
every 6 hours on GitHub Actions. On any fetch failure the previous
`data.json` is kept, so a failed run never clears real sightings.

Verified live in this session (15 Nov 2026): the query returns real
records — most recently an orca on 7 Nov 2026, harbour seal at Ham,
Thurso, and grey seals at Keiss and Auckengill on 15 Oct 2026.
Seals dominate this feed; it is one feed, not the whole picture.

## Sources — verification log (15 Nov 2026)

Live feed vs curated link per source. Every URL below was verified
live in this session (page opened, search result with content, or
HTTP 200). Nothing was guessed.

### Live data

| Source | What it is | URL | Status |
|---|---|---|---|
| iNaturalist API | Public sightings in the Caithness box; the site's live feed | https://api.inaturalist.org/v1/observations | LIVE — tested, returns records |
| OBIS | Global ocean biodiversity archive; API works for this coast (847 orca records in the box, most recent 2018) — an archive, not a live feed | https://obis.org/ | API verified working |

### Live pages (open the page; no API)

| Source | What it is | URL | Status |
|---|---|---|---|
| Sea Watch Foundation — Recent Sightings | Recent sightings from all platforms, with map view | https://www.seawatchfoundation.org.uk/recent-sightings/ | LIVE page (HTTP 200) |
| Sea Watch Foundation — Orca Watch sightings | Orca Watch sightings by day | https://www.seawatchfoundation.org.uk/orca-watch-sightings/ | LIVE page (HTTP 200) |
| HWDT Whale Track — sightings map | Live sightings map (west-coast focused) | https://whaletrack.hwdt.org/sightings-map/ | LIVE page |

### Curated links (visit the page; no feed)

| Source | What it is | URL | Status |
|---|---|---|---|
| Sea Watch Foundation | UK cetacean monitoring; submit a sighting; Sea Watcher app; Orca Watch | https://www.seawatchfoundation.org.uk/ | Verified |
| Sea Watch — submit a sighting | Online sighting form | https://www.seawatchfoundation.org.uk/sightingsform/ | Verified |
| Sea Watch — sightings app | Sea Watcher app | https://www.seawatchfoundation.org.uk/sightings-app/ | Verified |
| Orca Watch | Annual nine-day event, hub John o' Groats; next 29 May – 6 Jun 2027 | https://www.seawatchfoundation.org.uk/orca-watch/ | Verified |
| Orca Watch — Facebook page | Event page | https://www.facebook.com/orcawatchers | Verified (Sea Watch's own site) |
| Orca Watch — Facebook group | Event group | https://www.facebook.com/groups/orcawatch/ | Verified (Sea Watch's own site) |
| WDC Shorewatch | Trained-volunteer 10-minute surveys; 1,053 volunteers, 100,000 watches since 2005 | https://uk.whales.org/whales-dolphins/how-we-help/shorewatch-scotland/ | Verified |
| HWDT Whale Track — about | About the platform | https://www.hwdt.org/whale-track/ | Verified |
| HWDT — Instagram | @hwdt_org | https://www.instagram.com/hwdt_org/ | Handle verified in HWDT's own spotters guide |
| SMASS — report a stranding | Scottish Marine Animal Stranding Scheme; dead strandings 07979 245 893, reports@strandings.org | https://strandings.org/report/ | Verified |
| SMASS — Instagram | @Strandings | https://www.instagram.com/Strandings/ | Handle verified in SMASS's own infographic |
| BDMLR | Live strandings, 24h: 01825 765 546 | https://www.bdmlr.org.uk/ | Verified (HTTP 200) |
| NatureScot — marine mammals | Marine mammal pages + Scottish Marine Wildlife Watching Code | https://www.nature.scot/plants-animals-and-fungi/mammals/marine-mammals | Verified |
| NatureScot — dolphins, whales and porpoises | Species pages; seven common cetaceans | https://www.nature.scot/plants-animals-and-fungi/mammals/marine-mammals/dolphins-whales-and-porpoises | Verified |
| Marine Directorate (gov.scot) | Marine mammal policy; SMASS funding | https://www.gov.scot/policies/marine-environment/marine-mammals/ | Verified |
| NBN Atlas | Searchable UK wildlife records atlas | https://nbnatlas.org/ | Verified (HTTP 200); API not verified |
| Caithness Field Club | 2005 cetacean bulletin — local how-to | http://caithness.org/caithnessfieldclub/bulletins/2005/caithnesscetaceans.htm | Verified |
| The Broch Project — Pentland Firth | The Firth, "the UK's top location for spotting orca" | https://www.thebrochproject.co.uk/locations/the-pentland-firth | Verified |
| The Broch Project — Dunnet Head | Most northerly point; wildlife | https://www.thebrochproject.co.uk/locations/dunnet-head | Verified |
| The Broch Project — Whales | Whales off Caithness | https://www.thebrochproject.co.uk/locations/whales | Verified |
| Wild Coastal Trail | Highland Council eight-site trail leaflet (PDF) | https://pentlandlodgehouse.co.uk/wp-content/uploads/2014/11/Wild_coastal_trail___Caithness.pdf | Verified |

### Named, no public link verifiable

| Source | What it is | Note |
|---|---|---|
| Caithness & Moray Firth Cetacean Sightings (Facebook group) | The fastest local news — real-time tip-offs and photos; the 27-orca pod of 7 Nov 2026 was reported here. Existence verified in multiple independent sources. | No direct group URL could be verified — search Facebook for the group name. Do not guess the URL. |
| Marine Conservation Society — Basking Shark Sightings Project | Where basking shark reports go. | Named in a source; URL not verified in this session. |
| Orca Watch WhatsApp sightings group | Runs during Orca Watch for up-to-the-minute sightings. | Mentioned in a 2022 trip report; no public join link. |

### Not used

- Sea Watch "map viewer" standalone URL
  (`seawatchfoundation.org.uk/map-viewer/`) — returns 404; the map
  lives inside the Recent Sightings page instead.
- NBN Atlas API — the endpoint tried returned an error page; the
  website is linked instead.
- Facebook/Instagram feeds — no open feeds exist; socials are curated
  links only, never presented as live.

## Facts used on the site, and where they came from

- Orca Watch: nine days, late May/early June, hub John o' Groats;
  next 29 May – 6 Jun 2027; applications open in January
  (Sea Watch Foundation).
- Orca Watch 2022 counts: orca 58, minke 44, Risso's 44, bottlenose
  18, common 6, humpback 2 (WDC blog).
- 7 Nov 2026: pod of 27 orcas ("the 27s") from Ackergill to
  Duncansby to John o' Groats (Caithness & Moray Firth Cetacean
  Sightings post; same date on iNaturalist).
- 24 May 2026: four orcas from Brough Bay (Sea Watch Orca Watch
  sightings). 8 June 2022: "64s" pod within 30 feet at Auckengill
  (trip report).
- Pentland Firth: 14 miles long, 8 miles across at its widest; "the
  UK's top location for spotting orca" (Broch Project).
- Seven relatively common cetaceans in Scottish waters: bottlenose
  dolphin, harbour porpoise, minke whale, white-beaked dolphin,
  Risso's dolphin, common dolphin, orca (NatureScot). Common dolphins
  mainly May–October (NatureScot).
- Shorewatch seasonal peaks: minke June–July, Risso's late summer,
  harbour porpoise autumn, bottlenose/common summer (WDC Shorewatch
  trend report 2025).
- Grey seal: more common than harbour seal around the Firth; white
  pups October–January. Harbour seal pups May–July (Pentland Firth
  sources). Harbour seals overwinter on islands in the River Thurso
  (Caithness).
- Dunnet Bay: porpoises in summer; both seal species haul out; Gills
  and Brough Bays the best viewpoints (caithness.org).
- Sandside Head: ranger-led sea watches during National Whale &
  Dolphin Watch, late July (High Life Highland).
- Watching tips: calm days, early morning/late afternoon light,
  headlands with height, seabird flocks mark food (Caithness Field
  Club).
- Strandings: live — BDMLR 01825 765 546, SSPCA 03000 999 999;
  dead — SMASS 07979 245 893, reports@strandings.org (SMASS,
  gov.scot, SMRU). Do not push a live animal back to sea; keep quiet,
  keep dogs and children away.
- Shorewatch: 1,053 volunteers, 100,000 watches since 2005,
  18 species (WDC).
- Sea Watch database: 300,000+ sightings over 50 years
  (Sea Watch Foundation accounts).

## Design

Same family as the Rectory Naturecam: Patagonia palette (forest
#1f3d2b, ochre #d9a441, rust #c65d21, stone cream #f4efe4), Archivo
Black display type, grain texture, flat hand-drawn SVG glyphs.
No photographs, no AI-generated imagery.

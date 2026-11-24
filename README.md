# Japan VPS: what a Tokyo server costs, how small a plan a shop or Minecraft server can get away with, and where Evoxt's $4.99 tier stops being enough (full plan table)

A Tokyo VPS costs $4.50 to $8 a month for the first 1–2 GB of RAM, and the size most people actually need is a 2 GB box in the $6 range. Evoxt's VM-1 sits at the cheap end of that band: 1 core rated up to 6.0 GHz, 2 GB RAM, 20 GB storage, a Tokyo location and **$5.99/month**, with weekly backups included. The same 2 GB tier is $8.00 at ExtraVM and $7.71 at LightNode.

Below is the full Evoxt plan list with prices, what Tokyo actually buys you in milliseconds, how the Japanese options compare on port speed and transfer, and the four things worth confirming before you pay.

> **Quick pick:** Evoxt VM-1, 2 GB RAM, $5.99/month, Tokyo. Enough for a small shop, an API backend, a WireGuard relay, or a lightly modded Minecraft server with a handful of players. It undercuts the 2 GB tier at ExtraVM and LightNode, and weekly backups come with the plan rather than as an add-on.
> 👉 See the VM-1 plan and its current Tokyo price

## Every Evoxt plan, and which size you actually need

Evoxt sells 11 plan sizes on one price list, all with KVM virtualisation, full root, IPv4 and IPv6, weekly backups and a CPU rated up to 6.0 GHz. Prices are in USD and billed monthly; the pricing page also offers prepayment terms from one month up to three years, plus account credit you can top up and let the system draw down.

| Plan | vCPU / RAM | Storage | Monthly transfer | Price | Order |
| --- | --- | --- | --- | --- | --- |
| VM-0.5 | 1 core / 512 MB | 5 GB | 250 GB | $2.99/mo | [ Deploy](https://bit.ly/EvoXt) |
| VM-0.75 | 1 core / 1 GB | 10 GB | 250 GB | $4.99/mo | [ Deploy](https://bit.ly/EvoXt) |
| VM-1 | 1 core / 2 GB | 20 GB | 500 GB | $5.99/mo | [ Deploy](https://bit.ly/EvoXt) |
| VM-1.5 | 2 cores / 2 GB | 20 GB | 500 GB | $6.95/mo | [ Deploy](https://bit.ly/EvoXt) |
| VM-2 | 2 cores / 4 GB | 30 GB | 1 TB | $11.99/mo | [ Deploy](https://bit.ly/EvoXt) |
| VM-3 | 4 cores / 4 GB | 30 GB | 1 TB | $14.99/mo | [ Deploy](https://bit.ly/EvoXt) |
| VM-4 | 4 cores / 8 GB | 60 GB | 2 TB | $23.99/mo | [ Deploy](https://bit.ly/EvoXt) |
| VM-6 | 8 cores / 8 GB | 60 GB | 2 TB | $29.99/mo | [ Deploy](https://bit.ly/EvoXt) |
| VM-8 | 8 cores / 16 GB | 80 GB | 3 TB | $47.99/mo | [ Deploy](https://bit.ly/EvoXt) |
| VM-12 | 16 cores / 16 GB | 80 GB | 3 TB | $60.95/mo | [ Deploy](https://bit.ly/EvoXt) |
| VM-16 | 16 cores / 32 GB | 100 GB | 5 TB | $95.99/mo | [ Deploy](https://bit.ly/EvoXt) |

Two things about that table that the page itself doesn't spell out.

**The smallest plan isn't a Tokyo plan.** VM-0.5 at $2.99 is listed for the US and UK rather than Japan, so the practical entry point in Tokyo is VM-0.75 at $4.99 with 1 GB. If you specifically want Tokyo, confirm the location dropdown before you get attached to a plan size.

**The transfer column may lag what Tokyo actually gets.** The pricing page shows 500 GB for VM-1, while a September 2026 plan tracker lists 1 TB for the Tokyo VM-1, and Evoxt runs a two-tier location system where premium locations get roughly half the standard transfer. Treat the numbers above as standard-tier figures and read the allowance off the deploy screen. The 20 GB disk on VM-1 is the real constraint here, not the bandwidth: a WordPress site with a few years of images will fill it, so plan on offloading media or buying a bigger tier.

## What Tokyo latency looks like, and where Evoxt's routes fall short

ExtraVM publishes the clearest numbers for a Tokyo box, and they're a fair baseline for any provider in the city: under 10 ms inside Japan, 30–40 ms to South Korea, 40–60 ms to Taiwan and Hong Kong, and 110–130 ms to the US west coast.

Evoxt doesn't publish a per-region latency table. The hard data comes from a third-party benchmark run in July 2024 on a Tokyo VM-2 (2 cores reporting around 3.69 GHz, 3.8 GB usable RAM, Debian 11, KVM, network registered to AS149440 Evoxt Enterprise, location Asagaya-minami, Tokyo):

- Disk I/O averaged **2,355 MB/s** across three runs, which is NVMe behaviour, not spinning-disk emulation.
- A Tokyo speedtest node returned **1,319 Mbps up / 9,251 Mbps down at 1.00 ms**. Whatever the port is, it isn't a 100 Mbps cap.
- Los Angeles 98 ms, Dallas 146 ms, Amsterdam 234 ms.
- Hong Kong 49 ms but only 4.89 Mbps up and 0.92 Mbps down. Chongqing 217 ms at 2.65 Mbps up and 0.20 Mbps down.

That last line matters more than the first three. **Tokyo is close to Japan and acceptable to the US west coast, and on this evidence it is not a China-optimised route.** If your users are in Shanghai or Shenzhen, a generic Tokyo box won't fix their experience; you need a provider selling a China-specific route, which is a different product at a different price. Buyers who assume "close to Japan, therefore good for Asia" get burned here.

Evoxt also sells Osaka, which third-party testing puts at 7–8 ms from Tokyo, 50–55 ms from Shanghai and 55–60 ms from Hong Kong, with the same plan prices but roughly half the monthly transfer because Osaka counts as a premium location. For a mostly-western-Japan audience or a China-leaning one, Osaka is the better pick; for Korean and Taiwanese users, Tokyo's the one.

## How Evoxt's Tokyo pricing compares with ExtraVM, LightNode and KernelHost

Same city, wildly different products. This is what the first paid tier looks like across four providers, all figures as published by each company.

| Provider | Entry Tokyo plan | Price | What changes |
| --- | --- | --- | --- |
| Evoxt | VM-0.75: 1 core / 1 GB / 10 GB / 250 GB | $4.99/mo USD | VM-1 gives 2 GB for $5.99; weekly backups included |
| ExtraVM | 1 core / 1 GB / 15 GB NVMe / 1 TB / 1 Gbps | $4.50/mo USD | Anti-DDoS included at no extra cost; 5-day refund, fiat payments only |
| LightNode | 1 vCPU / 2 GB / 50 GB NVMe / 1 TB | $7.71/mo USD | 50 GB storage on every tier, including the $52.70 one |
| KernelHost | "from €23.99/mo" | EUR | Unlimited traffic, 20 GB SSD, no IPv6 on Edge VPS |

Read the KernelHost line carefully. Its Japan page says "From €23.99 per month", but the plan card actually rendered on that page is €94.99/month for 16 GB RAM and 4 vCPU, and the page never explains which configuration the €23.99 refers to. On top of that, €23.99 and $4.99 aren't the same scale, so a straight number comparison is meaningless without converting. KernelHost's Edge VPS is also explicit that IPv6 isn't offered and that it can't promise which country a geolocation service will assign to your IPv4 address. Its selling point is unlimited traffic at up to 1 Gbps, not cheap RAM.

The pattern across this table is that "Japan VPS" spans roughly a 5x price range for what looks like similar specs, and the differences are in port speed, transfer allowance and whether backups, DDoS filtering and IPv6 are in the price. ExtraVM's $4.50 buys DDoS protection and a 5-day refund window but only fiat payment methods for that refund. Evoxt's $5.99 buys the weekly backup and both IP stacks. LightNode's $7.71 buys 50 GB of disk and a Windows option. Nobody is cheapest on every axis.

If your workload is a 2 GB web app and you want the lowest monthly number with backups included, Evoxt's VM-1 is the pick.
👉 Open the Evoxt plan list and check the Tokyo price for VM-1

## Pick a plan by workload

**Small site, blog, brochure shop, or a Laravel/Node API for a few hundred daily users.** VM-1 at $5.99. One fast core, 2 GB and 20 GB is enough until the database and the media library start competing for disk. Step up to VM-2 only if you're running WooCommerce with a real catalogue and no caching layer.

**Minecraft, vanilla or a light modpack, 10–20 players.** VM-2 at $11.99 gets you a second core and 4 GB. Minecraft is single-thread bound, so the high clock rating matters more than core count here, and 4 GB is the practical floor for anything with mods.

**Palworld, ARK, or a heavily modded Minecraft server.** VM-4 at $23.99 with 4 cores and 8 GB. These servers leak memory and spawn threads; 4 GB will fall over with more than a few players.

**WireGuard or a proxy relay in Tokyo.** VM-0.75 at $4.99. A VPN endpoint does almost no work, and 250 GB of transfer covers personal use comfortably. Don't buy more RAM for this.

**Dev and staging boxes.** VM-0.75 again, but note Evoxt bills monthly through to multi-year prepay, so a two-day test still costs a month. Spin it up, do the work, cancel.

**What most people don't need.** VM-8 and above. The 16-core VM-12 at $60.95 and VM-16 at $95.99 exist for hosts running several game instances or a database under real concurrency. If you're reading this to host one site, buying 16 cores is $55 a month spent on nothing measurable.

## What to confirm on the order screen

**Where the IP is registered.** The 2024 Tokyo benchmark showed the address as JP, in the Asagaya-minami range under Evoxt's own ASN, which is what you want for ad verification, localisation testing or Japanese streaming checks. Geolocation databases disagree with each other, so run your own check after deployment before you build a workflow on it.

**IPv6.** Included on Evoxt, and the benchmark showed both stacks online. KernelHost's Edge VPS has none at all, and HOSTKEY bundles an IPv6 /64 with every server. If your stack needs IPv6, this single line rules providers in or out.

**DDoS protection.** ExtraVM includes filtering on every Tokyo plan at no extra charge and KernelHost advertises 3.2 Tbps, but Evoxt's pricing page doesn't state DDoS protection at all, and HOSTKEY only promises free basic protection in Europe. If you're running a game server that attracts attacks, ask support directly rather than assuming.

**Transfer metering.** Evoxt meters monthly transfer by plan (250 GB to 5 TB). HOSTKEY meters outbound traffic according to the traffic plan you pick. KernelHost's Edge line is unmetered. A video or download-heavy site needs the unmetered option; a normal web app will never touch Evoxt's 500 GB.

**Refund terms.** Evoxt's pricing page doesn't publish a refund window. Third-party setup guides cite a 14-day money-back guarantee with a full refund available inside the first 24 hours, but that isn't on the page you pay from, so get it confirmed in writing through support before you commit to a multi-year prepay. Payment methods on the official page are credit and debit cards, PayPal, Bitcoin and USDt on Tron.

If you're serving users in Japan on a budget under $10 a month, VM-1 at $5.99 is the default and VM-2 at $11.99 is the upgrade you make when a game server or a database actually needs the second core. Check the transfer allowance on the deploy screen, and ask support about DDoS and refunds if either one decides the purchase for you.

👉 Deploy a Tokyo VM on Evoxt

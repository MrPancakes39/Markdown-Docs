# The heck is an "nmap"?
- "Netwrok Map":
	* Sorta like a radar, except we can change how it scans.
	* Get a map of our network/attack surface.
- Widely considered one of the most important tools to know.

# Scan Types
- TCP Syn (`-sS`):
	* Syn Scan is a half-open scan with service detection.
- Service Version (`-sV`):
	* Basic enumeration of services to determine version of them.
- UDP (`-sU`):
	* Can take a while to complete.
	* Recommended for thoroughness.
	* Perfect opportunity for 'popular ports' scan (top ~100)

# Switches to Know
- Help Menu:
	* `-h`, `--help`.
- Operation System Detection (`-O`):
	* Capital o, not a zero.
- Verbose (`-v <num>`):
	* Set verbosity.
	* Very verbose (`-vv`).
- Ports to Scan (`-p <num>`):
	* `-p 1-65535` (range).
	* `-p 21` or `-p21` (to scan port 21).
	* `-p-` (to scan every port).
- Aggressive Scan (`-A`):
	* Sets many of enumeration options to true (like `-O`, `-sV`, and `-sC`).
- Timing (`-T<num>`):
	* `-T1`: Also called Paranoid because it's the slowest timing.
	* `-T3`: This is the default timing speed. (It's good, but if you want faster recommended `-T4`).
	* `-T5`: Also called Insane because it's the fastest timing.
- Don't Ping (`-Pn`):
	* Useful in the case that the host firewall doesn't let ICMP traffic through.
- Output:
	* `-oX`: XML Output.
	* `-oG`: Greppable Output. (Nice for searching through using grep as the name would imply.)
	* `-oN`: Nmap Plain Text Output.
	* `-oA`: All Outputs.
	* Example: `-oX ./networkScan.xml`.

# Nmap Scripting Engine (NSE)
Three basic commands to know here:
- Default scripts (`-sC`):
	* Runs default scripts, only safe scripts.
	* Doesn't risk crashing/damaging the target host.
	* Equivalent to `--script default` or `--script=default`.
- `--script <category/script_name>` or `--script=<category/script_name>`.
- `--script vuln` or `--script=vuln`:
	* Scans with all scans from the vulnerability check caegory.


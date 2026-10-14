# Overgrowth Style Blood & Ragdolls 0.1

Overgrowth-style blood effects and active dying ragdolls for **S.T.A.L.K.E.R. Anomaly**. Both editions include the blood and ragdoll features.

## Downloads

Download the appropriate **0.1 release ZIP** from the [**0.1 release page**](https://github.com/johbowfor/overgrowth-style-blood-and-ragdolls/releases/tag/v0.1):

- **Base Anomaly:** Anomaly 1.5.3 with the standard DX11 shader setup.
- **Zona SSS23.5:** Zona on Anomaly 1.5.3 using its SSS23.5 graphics profile.

Both use the supplied custom **DX11-AVX executable and native DLLs**. The Zona edition includes its matching shader integration; additional shader overhauls require a matching integration.

## Installation with MO2

1. Close the game. Install the appropriate ZIP through MO2, enable it, and let its files win the required conflicts. Keep one edition of this mod enabled.
2. **COPY THE CONTENTS OF THE MOD'S `bin` FOLDER INTO THE ACTUAL ANOMALY INSTALLATION'S `bin` FOLDER. BACK UP THE FILES BEING REPLACED!** Ordinary MO2 installation does not replace the physical executable. A correctly configured root-deployment plugin can manage these files instead.
3. With the game closed, clear the contents of `appdata\shaders_cache\r4` in the Anomaly installation, or use the launcher's shader-cache option. If MO2's Overwrite contains the same cache, clear that cache too. Keep saves and other appdata files.
4. Launch the supplied `bin\AnomalyDX11AVX.exe` through MO2. The first load may take longer while shaders compile.

MCM is optional and is included in Zona. MCM **1.72** was used for integration checks. Without it, the supplied configuration defaults apply.

## Features

- Projected bullet entry and exit wounds with independently adjustable sizes.
- Projected melee slash wounds with their own size settings.
- Blood streaks attached to character UV maps and moving with the body.
- Ongoing **visual bleeding (VB)** driven by **Anomaly bleeding (AB)**. The game's damage, bleeding, and healing mechanics remain unchanged.
- Wound severity affects visual emission and stream travel.
- Penetration sprays and fatal neck-shot arterial sprays.
- Droplets stain scenery and nearby characters. Neck droplets can also stain their source character.
- Ground-drop growth and merging, wall splats, and downward runoff.
- Blood impact sounds, wet/dry appearance, distance detail, and lifetime controls.
- Body-blood cleanup when medical treatment stops AB, or when a medical item is used after AB has stopped. Natural bleeding cessation leaves marks until another cleanup condition applies.
- Cleanup when corpses are removed and timed blood expiry.
- Active flailing, guarding, and wound-reaching ragdoll reactions.
- Finishing-hit reactions, anatomical knee limits, and stable detail bones. Further refinement is still needed.

## MCM settings

Open **MCM → Blood & Ragdolls**. There are **89 controls across 14 pages**:

General; Wound Appearance; Body Blood Appearance; Visual Bleeding (VB); Penetration Sprays; Neck Arterial Sprays; Ground & Wall Blood; Wetness & Drying; Cleanup & Performance; Ragdoll Reactions; Advanced Physics; Advanced Body-Part Weights; Advanced Rendering; Diagnostics.

**Click Apply, then restart the game.** Settings are read once at startup. **Default** restores the selected page; click Apply to save its defaults. New wound sizes affect new wounds.

Bullet trail debug, ragdoll diagnostic logging, and physics recording default **off**. Bullet trail debug is independent of the launcher's debug flag.

Without MCM, edit `gamedata\configs\overgrowth_blood.ltx` and `gamedata\configs\mod_system_active_ragdoll.ltx`, then restart.

### Settings details

- Tint, opacity, wet shine, and distance mip controls affect character UV blood.
- The drying multiplier affects body, ground, and wall blood. Other scenery projector splats retain their own drying behavior.
- Body-blood lifetime starts with the first stain in an accumulation; later hits do not reset it. Continuing AB can produce fresh VB after that blood clears.
- New airborne droplets replace the oldest when the limit is reached.
- Wall runoff chance controls initiation; overlapping blood can join a drip.
- Body-part drive weights apply where the skeleton has the corresponding physical joint. Anatomical limits and detail-bone stability remain in place.
- Increasing texture resolution increases both dimensions and memory use.

## Credits and thanks

Overgrowth code and adapted blood/motion components: **Wolfire Games LLC**. Bullet Physics: **Bullet contributors**. S.T.A.L.K.E.R. Anomaly and X-Ray Monolith: their respective contributors. Zona and its shader modifications: their respective creators.

A big thanks to Dave and Wolfire Games for allowing me to modify and implement their revolutionary Overgrowth ragdoll and blood tech into Stalker Anomaly. They are the giants upon whose shoulders us blood and ragdoll modders stand. They pioneered this technology years ago and are worthy of the highest praise for creating such a unique system that was so ahead of its time.

All I have done is port and humbly tweak their great work for STALKER Anomaly. Buy their games Overgrowth and Receiver. They are both very unique titles.

Third-party license notices are included in `LICENSES` and in both download packages.

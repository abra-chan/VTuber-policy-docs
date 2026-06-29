# Security Policy – Das Hünerhaus

## Introduction
This document outlines security best practices for all streaming-related accounts and the Discord server. It exists to protect both the streamer and the community while maintaining clear delegation of responsibilities.

## Disclaimer
This is **not** sponsored by 1Password (my audience isn’t big enough for their affiliate program… yet).

## Passwords
1. Generate strong, unique passwords for every streaming-related account.
2. Store all credentials in a **1Password vault**.
3. Review and update credentials on a regular schedule (at least weekly).

## Two-Factor Authentication (2FA)
1. Enable **TOTP** (Time-based One-Time Password) wherever supported and store the codes in 1Password.
2. Save backup codes in a secure note titled “Backup Codes”.
3. Avoid email or SMS-based 2FA when possible — these are considered less secure and have been deprecated by NIST recommendations.

## Streaming Security
1. Use **RTMPS** (secure RTMP) on all platforms that support it. Add the “S” to your server URL (e.g., `rtmps://...`).
2. Enable stream authentication where available and store the credentials securely in OBS.
3. Never share stream keys publicly.

## API Keys & Secrets
1. Store all API keys, secrets, and tokens in the 1Password vault.
2. Never hard-code them in OBS or public scripts. Use environment variables instead (e.g. ~/bash_profile).

---

## Discord Server Security

### Objective
Maintain full sovereignty over the server while safely delegating moderation duties to a small number of trusted individuals.

### Core Principles
- Permissions are assigned to **roles**, not individual users.
- Members should hold **only one functional role** at a time.
- Higher roles inherit permissions from lower ones (bottom-up hierarchy).
- Use category-level permissions with overrides only when necessary.

### Terms Used in This Document
- **See** = View Channel  
- **Chat** = Send Messages / Speak (voice)  
- **Listen** = Connect to voice  
- **Present** = Video / Screen Share  
- **Buzz** = Use Soundboard  
- **Prio** = Priority Speaker  
- **Mod** = Manage Messages / Moderate Members

### Functional Roles (Hierarchy)

| Role                  | Purpose                              | Level  |
|-----------------------|--------------------------------------|--------|
| **Brood Lord**        | Owner + trusted alts + critical bots | Top    |
| **Brood Inquisitor**  | Full Moderators                      | High   |
| **Brood Warden**      | Trial Moderators                     | Mid    |
| **Brood Keeper**      | Bots (3rd party)                     | Mid    |
| **VIP Hühner**        | Loyal supporters & contributors      | Member |
| **Brood Supporter**   | Tier 1 Subscriber perks              | Member |
| **Chooks**            | Verified + sorted into a Great House | Member |
| **Cheeps**            | Accepted rules but not yet sorted    | New    |
| **Everyone**          | Brand new users                      | Base   |

---

### Permissions by Role (Summary)

**Everyone** (Base)
- See: `#newcomers`, `#rules`, `#feeding-schedule`, `#dinner-bell`
- React: `#rules`

**Cheeps**
- All of the above, plus:
- See: `#the-compost-pile`, `#the-yard`, `#coq-a-doodle`, `#front-lawn-frisbee`, `#fight-club`, `#afk-roost`
- React & Chat in: `#the-compost-pile`, `#the-yard`
- Chat in threads in: `#initiations`, `#the-compost-pile`, `#the-yard`

**Chooks**
- All previous permissions, plus:
- See: `#roles`, `#backyard-arnold-palmer`, `#poules-propound`, `#poules-polls`
- React in: `#roles`, `#initiations`, `#coq-a-doodle`, `#poules-propound`, `#poules-polls`
- Create threads in public channels (as allowed by category)

**Brood Supporter**
- All previous permissions, plus:
- See & Chat in: `#poules-on-perch`, `#poules-en-direct`, `#poules-propound`
- React in: `#poules-propound`, `#poules-polls`

**VIP Hühner**
- All previous permissions, plus:
- (To be defined, possibly: enhanced emote/soundboard access, early access to certain features, or cosmetic perks)

**Brood Keeper**
- Show/hide channels: `#poules-on-perch`, `#poules-en-direct`, `#poules-polls`
- Chat in: `#dinner-bell`
- Create Threads in: `#initiations`
- Manage user roles (as needed for automation)

**Brood Warden**
- Moderation powers to be defined.

**Brood Inquisitor**
- Moderation powers to be defined.

**Brood Lord**
- Full Permissions, Administrator

### Temporary “Poules LIVE” Channels

A dedicated category called **“. ݁₊ ⊹ . ݁ ⟡ Poules LIVE ⟡ ݁ . ⊹ ₊ ݁.”** provides subscriber perks, primarily during streams. These channels are designed to be **functional and mostly temporary** rather than permanent private lounges.

#### Channels in “Poules LIVE”

| Channel Name       | Type  | Availability    | Visibility               | Posting Rights           | React Rights           | Purpose                                                     |
|--------------------|-------|-----------------|--------------------------|--------------------------|------------------------|-------------------------------------------------------------|
| `poules-propound`  | Text  | **Always open** | All **Chooks** + above   | **Brood Supporter** role | All **Chooks** + above | Drop videos to react, games to play, and jargon suggestions |
| `poules-polls`     | Text  | During stream   | All **Chooks** + above   | **Brood Keeper** + above | All **Chooks** + above | Live voting & quick polls                                   |
| `poules-on-perch`  | Voice | During stream   | **Brood Supporter** role | **Brood Supporter** role | N/A                    | Game queue / play requests                                  |
| `poules-en-direct` | Voice | During stream   | **Brood Supporter** role | **Brood Supporter** role | N/A                    | Live collab / subscriber voice                              |

#### Automation & Security Rules
1. Except for `#poules-propound`, channels in this category are revealed **only while the stream is live**.
2. **The Oracle** will reveal these channels and post a ping in `#dinner-bell` when the stream starts, then re-veil them when the stream ends.
3. Access to temporary channels is restricted to the **Brood Supporter** role (or higher).
4. The category is hidden again shortly after the stream ends to keep the main server feeling unified.

**Note on `#poules-propound`**: This channel remains permanently visible to all **Chooks** so supporters can submit suggestions at any time. Posting access is limited to the **Brood Supporter** role and above. This prevents the main channels from becoming cluttered while still giving value to regular contributors.

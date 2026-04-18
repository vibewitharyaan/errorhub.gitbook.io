---
icon: clock-rotate-left
---

# Changelog

{% updates format="full" %}
{% update date="2026-04-18" %}
## v3.3.0

<details>

<summary>Improvements &#x26; Refactor</summary>

* **Service Logic:** Refined `cutscene.only` mode to properly disable taxi and rental services.
* **System Stability:** Rewrote core service modules (taxi, rental, receptionist) for better performance and maintainability.
* **Version Checker:** Completely rebuilt for more reliable update notifications and cleaner logs.

</details>

<details>

<summary>Fixed</summary>

* **Gender Detection:** Switched to framework-based detection for 100% reliability, ensuring the correct cutscene plays regardless of the player's ped model.

</details>

<details>

<summary>Improved</summary>

* Optimized code structure and improved formatting across all client-side files.

</details>

<details>

<summary>Notes</summary>

Updated files:

* `client/cl_cutscene.lua`
* `client/cl_main.lua`
* `client/cl_rental.lua`
* `client/cl_taxi.lua`
* `server/version.lua`
* `shared/bridge.lua`
* `fxmanifest.lua`

</details>
{% endupdate %}

{% update date="2025-12-17" %}
## v3.2.5

<details>

<summary>Added</summary>

* Introduced face customization support (face blending for increased variation)
* Added a configuration guide with detailed explanations for all options

</details>

<details>

<summary>Changed</summary>

* Updated the component system to improve compatibility

</details>

<details>

<summary>Fixed</summary>

* Resolved issues where passenger skin tones were not applying correctly
* Resolved issues where passenger hairstyles and colors were not applying correctly

</details>

<details>

<summary>Improved</summary>

* Enhanced overall reliability of the clothing system

</details>

<details>

<summary>Notes</summary>

* This is the final release of Advanced Cutscene. No further updates are planned.
* Updated files:
  * config/config.lua
  * client/cl\_cutscene.lua

</details>
{% endupdate %}

{% update date="2025-12-02" %}
## v3.2.0

<details>

<summary>Added</summary>

* Introduced support for configurable passenger clothing

</details>

<details>

<summary>Changed</summary>

* Passenger models are now aligned with GTA V cutscene requirements to ensure proper outfit application

</details>

<details>

<summary>Fixed</summary>

* Resolved inconsistencies where passenger clothing would not apply correctly during cutscenes

</details>

<details>

<summary>Removed</summary>

* Passenger ped model customization

</details>
{% endupdate %}
{% endupdates %}

{% updates format="full" %}
{% update date="2025-10-14" %}
## v3.1.0

<details>

<summary>Added</summary>

* Introduced support for using any multiplayer/NPC ped as a passenger (not limited to freemode models)

</details>

<details>

<summary>Fixed</summary>

* Resolved an issue where passenger outfits for freemode characters would not apply correctly during cutscenes

</details>
{% endupdate %}
{% endupdates %}
